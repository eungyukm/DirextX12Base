# DirextX12Base        
 DirexX12 기초 사항을 정리한 프로젝트입니다.       

# Computer Graphic란?          
 3D 오브젝트를 배치하고, 그것이 컴퓨터 화면에 2D로 표현되는 전 과정을 공부하는 학문입니다.         

# Computer Graphic를 공부하는 이유          
 Unity와 Unreal Engine의 API를 사용하면, Computer Graphic의 부분을 내부적으로 처리해줍니다.            
 게임 엔진의 내부적인 작동원리를 이해할 수 있습니다.          
 
# GPU의 필요성        
  모든 물체들은 삼각형으로 이루어져 있습니다.       
  정점에 대한 좌표 연산을 해야 합니다.       
  위치와 색상에 대한 연산을 해야 합니다.        
  CPU가 모든 계산을 하기 보다는, GPU에 할당하여 연산하도록 합니다.       

# 렌더링 파이프라인
  Input-Assembler Stage : 정점의 정보를 전달하는 역할         
  Vertex Shader :        
  
  Hull Shader Stage        
  Tesselator State          
  Domain Shader Stage           
  
  Geometry Shader State : 새로운 정점들을 생성할 때 활용             
  Stream Output Stage               
  Rasterizer Stage :            
  Pixel Shader Stage : 최종적으로 색상을 입히는 단계         
  Output Merger Stage             

# DirectX 목차       
[1. DirextX]()
[2. 프로젝트 설정](https://github.com/eungyukm/DirextX12Base/wiki/01.-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EC%84%A4%EC%A0%95)
 
