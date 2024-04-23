# GetComponent Attribute

필드 이름과 같은 GameObject를 찾아서 필드와 동일 타입의 컴포넌트를 필드에 할당 해주는 어트리뷰트 입니다.

### 설치방법
1. 패키지 관리자의 툴바에서 좌측 상단에 플러스 메뉴를 클릭합니다.
2. 추가 메뉴에서 Add package from git URL을 선택하면 텍스트 상자와 Add 버튼이 나타납니다.
3. https://github.com/DarkNaku/Attribute_GetComponent.git 를 입력하고 Add를 클릭합니다.

### 사용방법
```csharp
    // 현재 게임 오브젝트에 있는 필드 타입의 컴포넌트를 가져옵니다.
    [SerializeField, GetComponent] 
    private SpriteRenderer _spriteRenderer;

    // 현재 오브젝트의 모든 자식의 동일 필드 타입의 컴포넌트 중 필드 이름과 동일한 컴포넌트를 가지고 옵니다.
    [SerializeField, GetComponentInChildren]
    private BoxCollider _cubeA;
    
    // 현재 오브젝트 모든 자식의 동일 필드 타입의 컴포넌트 중 기재한 동일한 이름의 오브젝트 컴포넌트를 가지고 옵니다.
    [SerializeField, GetComponentInChildren("Cube B")]
    private BoxCollider _boxColliderB;
    
    // 현재 오브젝트 모든 자식의 동일 필드 타입의 컴포넌트들을 가지고 옵니다.
    [SerializeField, GetComponentsInChildren]
    private BoxCollider[] _cubes;
    
    // 현재 오브젝트 모든 자식 중 기재한 이름과 동일한 오브젝트의 동일 필드 타입의 컴포넌트들을 가지고 옵니다.
    [SerializeField, GetComponentsInChildren("Sub")]
    private BoxCollider[] _subCubes;
    
    // 현재 오브젝트의 모든 부모의 필드 타입의 컴포넌트 중 필드 이름과 동일한 컴포넌트를 가지고 옵니다.
    [SerializeField, GetComponentInParent]
    private SpriteMask _parent1;
    
    // 현재 오브젝트 모든 부모의 필드 타입의 컴포넌트 중 기재한 동일한 이름의 오브젝트 컴포넌트를 가지고 옵니다.
    [SerializeField, GetComponentInParent("Parent 2")]
    private SpriteMask _spriteMask;

    // 모든 오브젝트의 동일 필드 타입의 컴포넌트 중 기재한 동일한 이름의 오브젝트 컴포넌트를 가지고 옵니다.
    [SerializeField, FindComponent] 
    private Canvas _canvasA;
    
    // 모든 오브젝트의 동일 필드 타입의 컴포넌트 중 기재한 동일한 이름의 오브젝트 컴포넌트를 가지고 옵니다.
    [SerializeField, FindComponent("Canvas B")] 
    private Canvas _canvas;
    
    // 모든 오브젝트의 동일 필드 타입의 컴포넌트들을 가지고 옵니다.
    [SerializeField, FindComponents] 
    private SphereCollider[] _sphereAll;
    
    // 모든 오브젝트들 중 기재한 이름과 동일한 오브젝트의 자식들 중 동일 필드 타입의 컴포넌트들을 가지고 옵니다.
    [SerializeField, FindComponents("Spheres")] 
    private SphereCollider[] _sphereTargets;
```

### 추가설명
* 기본적으로 명시하지 않는 대상 오브젝트를 찾을 때 필드명과 동일한 이름을 찾습니다. 단, 언더바('_')와 공백(' ')은 제거 한 후 모두 소문자로 변환하여 필드 이름과 비교합니다.
* 배열에 적용 할 때는 어트리뷰트를 적용 할 때 바로 동작 하지 않고 배열의 사이즈를 변경해야 동작합니다. 배열에 어트리뷰트를 처음 적용할 때 이벤트가 호출 되지 않는 문제가 있는데 해결 방법을 아시는 분은 저에게도 알려주시면 감사하겠습니다.
