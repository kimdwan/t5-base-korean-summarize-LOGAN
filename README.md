안녕 하세요 Ai hub에서 제공하는 기술과학 요약 데이터(참고)를 참고하여 파인튜닝한 모델입니다. 
사용방법은 아래와 같습니다. 
aihub데이터: https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&dataSetSn=71532


```
from transformers import T5ForConditionalGeneration,AutoTokenizer
path = "kimdwan/Breadcrumbst5-base-korean-summarize-LOGAN"
model = T5ForConditionalGeneration.from_pretrained(path)
tokenizer = AutoTokenizer.from_pretraeind(path)


#여기에 원하는 문장을 입력하시길 바랍니다. 
text= """ """
prefix = "summarize: " + text

token = tokenizer(prefix ,return_tensors="pt")
output = model.generate(input_ids=token["input_ids"],attention_mask = token["attention_mask"])
text = tokenizer.decode(output[0])[5:-4]
text
```

