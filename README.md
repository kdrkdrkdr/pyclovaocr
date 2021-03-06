# pyclovaocr

Unofficial python wrapper for [Clova AI OCR Service](https://clova.ai/ocr)

## Install
```bash
pip install pyclovaocr
```

## Usage

```python
from pyclovaocr import ClovaOCR

ocr = ClovaOCR()

result = ocr.run_ocr(
    image_path='kor_image.jpg',
    language_code='ko',
    ocr_mode='general'
)
print(result) 
'''
{'lines': [{'boundingBox': [[381, 462], [528, 461], [529, 521], [382, 522]],
            'id': 1,
            'wordIDs': [1]},
           {'boundingBox': [[214, 509], [524, 509], [524, 572], [214, 572]],
            'id': 2,
            'wordIDs': [2]}, ...
           
 'meta': {'domain': 'general',
          'imageSize': {'height': 800, 'width': 564},
          'language': 'ja',
          'version': 'general_rt__v2.2.0'},

 'words': [{'boundingBox': [[381, 462], [528, 461], [529, 521], [382, 522]],
            'confidence': 1.0,
            'id': 1,
            'isVertical': False,
            'text': '岩手山'},
           {'boundingBox': [[214, 509], [524, 509], [524, 572], [214, 572]],
            'confidence': 0.9989,
            'id': 2,
            'isVertical': False,
            'text': 'アトレッセンス'}, ...
'''
```


#### Supported Language Codes

Code | Description
--|--
ko | Korean
ja | Japanese
en | English


#### Supported Language OCR Modes

Modes | Description | Supported Language 
--|--|--
general | General OCR | ko, ja, en
receipt | Receipts | ko, ja, en
credit-card | Credit Cards | ko, ja, en
business-license | Business Licenses | ko
giro | Bills | ko
name-card | Business Cards | ko, ja, en
id-card | ID Cards | ko, ja
invoice | Invoice | ja
