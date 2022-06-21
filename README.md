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
  
  * 이미지만을 가지고 밀집된 인구수 **측정** 을 위해 해당 프로젝트를 진행하게 되었습니다.
  
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
  
  #### >데이터 전처리<
  
  <img src=https://user-images.githubusercontent.com/37567501/174828333-1d7b8011-d921-4ce8-9ef0-41b01773a774.png width="850" height="200"/>
  
  * 이미지 전처리 과정을 거치면 **파란색 배경의 이미지(정답지)** 와 같은 결과 값을 생성할 수 있다.
  
  #### >데이터 전처리 결과<
  
  <img src=https://user-images.githubusercontent.com/37567501/174628934-68b4f215-39b2-4afd-9123-3a8d23f1ab47.png width="850" height="400"/>
  
  #### >모델 선정<
  
  <img src=https://user-images.githubusercontent.com/37567501/174698126-77752e1c-d551-4be0-8c32-de101f3695ad.png width="850" height="400"/>
  
  * **환자 정보**가 담긴 엑셀은 **XGBoost** 모델, **내시경 이미지**는 **Yolov5** 모델을 활용해 감염여부를 확인할 수 있도록 선정하였습니다.
  
  
  <br/><br/>
  ---
  <br/><br/>
  
<div align="center">
  
  ### [수행결과]
  
  <br/>
  
</div>

  #### >모델 성능 결과값<
  
<div align="center">
  
  <img src=https://user-images.githubusercontent.com/37567501/174698327-87891964-fbce-4527-894d-4232ff1f26f6.png width="850" height="400"/>
  
</div>
  
  * **"Precision"** 값은 XGBoost와 Yolov5를 비교했을 때 차이가 거의 없으나, **"Recall"** 결과 값은 "XGBoost"가 현저히 떨어지는 것을 알 수 있다.
  
  <br/>
  
  #### >이미지 개수 따른 성능 비교<
  
<div align="center">
  
  <img src=https://user-images.githubusercontent.com/37567501/174633165-854e534a-553f-4b40-9eef-b08a9a3e9b1c.png width="850" height="400"/>
  
</div>

  * 빨간색으로 표시된 곳에 수치가 높으면 성능이 좋다고 볼 수 있는데 **학습할 수 있는 이미지가 많을수록 성능이 높아짐**을 확인할 수 있습니다.
  * 그래프 표에서 "metrics/precision"를 보면 **이미지가 적으면(1000개&5000개)** 더이상 **"precision"이 증가하지 않는** 것을 확인할 수 있습니다.
  * 결론 : "epoch" 증가 보다 **학습할 "데이터"** 양이 절대적으로 중요



  <br/>
  
  #### >서비스 구현<
  
<div align="center">
  
  <img src=https://user-images.githubusercontent.com/37567501/174630468-c50a73fb-88de-44bd-ac64-0d1f48e39d28.png width="850" height="400"/>

</div>

  * 웹서비스로 구현하여 인공지능(AI)의 예측을 확인할 수 있으며, 실제 의사의 진단과 비교 가능하게 만들어 **정확도**를 확인할 수 있습니다. (의사와 진단이 일치하는 결과값은 추가 학습에 사용 - **전이학습**)

  
  <br/><br/>
  ---
  <br/><br/>
  
  ### [개선사항]
  
<div align="center">
  
  <img src=https://user-images.githubusercontent.com/37567501/174631711-b299d9e3-fecf-4a30-a9f2-65d24cae2440.png width="850" height="400"/>
  
</div>

  > Stacking이란? 
  
  : 앙상블 기법은 머신러닝 모델의 성능을 향상할 때 많이 쓰이는 기법으로, 각 모델에서 예측한 값들을 가지고 최종 모델을 이용하여 한 번 더 target을 예측하도록 하여 모델의 예측 성능을 향상시킬 수 있는 기법입니다.
    
  <br/><br/>
  ---
  <br/><br/>
    
  ### [활용방안]
  
<div align="center">
  
  <img src=https://user-images.githubusercontent.com/37567501/174631207-5750d817-eeef-4132-a53c-1e2fde3882ca.png width="850" height="400"/>
  
</div>

  * 추후 내시경을 통해 실시간으로 결과값을 확인할 수 있도록 처리속도가 빠른 Yolov5 모델을 채택하였기에 실시간 탐지에 활용할 수 있습니다.
  
  
  ![Footer](https://capsule-render.vercel.app/api?type=waving&color=gradient&height=200&section=footer)

