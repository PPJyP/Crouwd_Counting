<div align="center">
  
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=300&section=header&text=밀집 인구수 분석 모델&fontSize=50" />
  
</div>

  프로젝트 소개에 앞서...
  1. **데이터 셋**과 학습된 **weight 파일**은 업로드 가능 사이즈 초과로 인해 업로드되지 못한 점 참고바랍니다.
  2. 정확도 비교를 위해 총 **3가지 모델(SANet, SCRNet, FIDTM)** 을 선정하여 비교 분석하였습니다.
  
  <br/>
  
<div align="center">
  
  ### [프로젝트 개요]
  
  <br/>
  
  <img src=https://user-images.githubusercontent.com/37567501/174822064-b09bdd04-428a-411c-a8c1-a257db3de02a.png width="850" height="400"/>
  
</div>
  
<div align="center">
  
  <br/><br/>
  ---
  <br/><br/>
  
  ### [수행과정]
  
  <br/>
  
</div>
  
  #### >데이터 수집<
  
  <img src=https://user-images.githubusercontent.com/37567501/174826514-6b01e79a-c9bd-415c-a461-74d75c2560c9.png width="850" height="400"/>
  
  * 데이터 셋은 "https://paperswithcode.com/dataset/shanghaitech"에서 수집하였으며, 그 외 다른 종류의 군중 데이터 셋도 참고할 수 있습니다.
  
  <br/>
  
  #### >데이터 전처리<
  
  <img src=https://user-images.githubusercontent.com/37567501/174828333-1d7b8011-d921-4ce8-9ef0-41b01773a774.png width="850" height="200"/>
  
  * 이미지 전처리 과정을 거치면 **파란색 배경의 이미지(정답지)** 와 같은 결과 값을 생성할 수 있다.
  
  <br/>
  
  #### >모델 선정<
  
  <img src=https://user-images.githubusercontent.com/37567501/174832714-2bcd1b0c-64cd-40d7-bac9-47929e584d86.png width="850" height="400"/>
  
  * 데이터셋 "ShanghaiTech_B"를 대상으로 높은 성능을 보인다는 3개의 모델 **SANet, SCRNet, FIDTM**을 선정하였습니다. (숫자가 **낮을수록** 성능이 좋음)
  
  <br/><br/>
  ---
  <br/><br/>
  
<div align="center">
  
  ### [수행결과]
  
  <br/>
  
</div>

  #### >모델별 비교 평가<
  
<div align="center">
  
  <img src=https://user-images.githubusercontent.com/37567501/174832114-12a2760d-a439-4a38-94c6-d3c581f739a1.png width="850" height="400"/>
  
</div>
  
  <br/>
  
  * 인구수 예측 오차가 낮은 순서는 테스트 결과 **FIDTM, SANet, SCRNet**이며, 세 개의 모델 중 평균적으로 **FIDTM이 좋은 성능**을 보여주었다. (또한 FIDTM이 **가시성**이 뛰어난 것을 볼 수있다.)
  
  <br/><br/>
  ---
  <br/><br/>
 
<div align="center">
  
  ### [개선사항]
  
</div>

  #### >개선사항_1<

<div align="center">
  
  <img src=https://user-images.githubusercontent.com/37567501/174836720-1ce3a868-d2d7-4385-967f-676d26f8ef83.png width="850" height="400"/>
  
</div>
  
  <br/>
  
  * 흑백 이미지에서 FIDTM 모델의 오차가 큰 이유는 FIDTM만 가지고 있는 모듈인 HighResolution 과정에서 컬러 이미지만 처리하도록 구현하여 문제가 발생한 것으로 판단됩니다. 이를 해결하기 위해서는 HighResolution 과정에 흑백 이미지 처리 과정을 추가가 필요해 보입니다.
  
  <br/>

  > HighResolution이란? 
  
  : 저해상도 이미지를 고해상도 이미지로 복원하는 과정을 통해 예측 정확도를 높이기 위한 기법입니다.
  
  <br/><br/>
  
  #### >개선사항_2<
  
  <img src=https://user-images.githubusercontent.com/37567501/174841859-aa344ec8-5ada-40ab-b794-4326c6f51ab2.png width="850" height="400"/>
  
  <br/><br/>
  
  #### >개선사항_3<
  
  <img src=https://user-images.githubusercontent.com/37567501/174842635-276ff3fb-4b86-4bd0-b6cb-9cf1eb29dacc.png width="850" height="350"/>  
  
  <br/><br/>
  ---
  <br/><br/>

<div align="center">
  
  ### [활용방안]

</div>
  
  #### >동영상 실시간 탐지 지원<
  
  <img src=https://user-images.githubusercontent.com/37567501/174844170-ed668fb2-686a-40c1-a920-8bf3cd37f44b.png width="850" height="400"/>

  <br/>
  
  #### >웹서비스 지원<
  
  <img src=https://user-images.githubusercontent.com/37567501/174845029-129687ca-fddd-4cc2-bf86-629ffb18e75f.png width="850" height="400"/>
  
  
  ![Footer](https://capsule-render.vercel.app/api?type=waving&color=gradient&height=200&section=footer)

