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
  Input-Assembler (IA) Stage 
  - 역할: 정점 버퍼, 인덱스 버퍼에서 데이터를 읽어 도형의 기본 정점 정보를 전달합니다.
  - 주요 작업: 정점 레이아웃, 프리미티브 타입 정의 (점, 선, 삼각형 등).

  Vertex Shader (VS) Stage
  - 역할 : 정점 위치, 색상, 텍스처 좌표 등을 변환합니다.
  - 주요 작업: 모델 공간 -> 월드 공간 -> 클립 공간 변환, 스키닝(본 애니메이션), 정점 조명.
  
  Hull Shader (HS) Stage        
  (선택적 단계, Tessellation 사용 시 활성화)
  - 역할 : 테셀레이션(세분화) 정도를 정의합니다.
  - 주요 작업 : Control Point 데이터를 수정하고, Tessellation Factor(분할 정도) 계산.

  Tesselator (Fixed-function State)
  - 역할 : Hull Shader에서 정의한 Factor를 바탕으로 프리미티브를 자동으로 세분화합니다.
  - 주요 작업: 삼각형, 사각형, 패치 등 기본 형상을 더 잘게 나눔.
    
  Domain Shader Stage (DS) Stage
  - 역할 : Tessellator에서 생성된 새로운 정점 위치를 결정합니다.
  - 주요 작업 : 곡면을 정의하고, 최종 정점 위치 계산.
  
  Geometry Shader (GS) State
  - 역할 : 프리미티브 단위로 입력을 받고, 추가 정점 또는 새로운 도형을 생성할 수 있습니다.
  - 주요 작업 : 실루엣 검출, 입자 시스템 구현, 그림자 볼륨 생성 등.

  Stream Output Stage          
  - 역할 : Geometry Shader에서 생성된 데이터를 메모리 버퍼로 저장합니다.
  - 주요 작업 : 결과 데이터를 다음 프레임 또는 다른 프로세스로 전달할 때 사용.

  Rasterizer Stage             
  - 역할 : 3D 공간의 정점을 2D 화면 공간으로 변환합니다.
  - 주요 작업 : Viewport 변환, Clipping, Back-face Culling(뒤집힌 면 제거), 삼각형을 픽셀로 분해.
    
  Pixel Shader Stage (PS) Stage
  - 역할 : 각 픽셀의 최종 색상과 조명 효과를 계산합니다.
  - 주요 작업 : 텍스처 매핑, 조명 계산, 그림자, 반사, 굴절 등 다양한 효과 처리.
         
  Output Merger (OM) Stage             
  - 역할 : Pixel Shader 결과를 프레임 버퍼에 최종적으로 출력합니다.
  - 주요 작업 : 블렌딩(투명도, 색상 조합), 깊이 테스트, 스텐실 테스트 수행.
