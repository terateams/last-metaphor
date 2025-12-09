```{mermaid}
%%| label: fig-spatial-topology
%%| fig-cap: "Spatial Topology of The Last Metaphor"

graph LR
    %% ==========================================
    %% 样式定义 (Style Definitions)
    %% ==========================================
    %% 增大字号，加粗边框，确保高对比度
    classDef default font-size:16px,stroke-width:3px;
    
    classDef core fill:#ffe6e6,stroke:#cc0000,color:#000,font-weight:bold;
    classDef functional fill:#e6f2ff,stroke:#005ce6,color:#000;
    classDef living fill:#e6ffe6,stroke:#009933,color:#000;
    classDef old fill:#f0f0f0,stroke:#333333,stroke-dasharray: 5 5,color:#000;
    classDef wild fill:#fffcf0,stroke:#e68a00,stroke-dasharray: 5 5,color:#000;
    
    %% 角色节点：深色背景+白色文字+圆角
    classDef char fill:#222,stroke:#000,color:#fff,shape:rect,rx:10,ry:10,font-size:14px;
    
    %% 连线样式
    linkStyle default stroke-width:2px,fill:none;

    %% ==========================================
    %% 区域定义 (Zones by SAI Gradient)
    %% ==========================================

    subgraph Zone0 ["核心区 / Zone 0 (SAI < 0.1)"]
        direction TB
        HY0(衡渊-零号<br/>Hengyuan-0):::core
        DuHeng(杜恒<br/>守门人):::char
    end

    subgraph ZoneStd ["标准功能区 / Zone Standard (SAI 0.1 - 3.0)"]
        direction TB
        
        %% 调整顺序：学术在上，工业在下，中间生活
        subgraph Academic [学术城]
            direction TB
            Inst(考古研究院):::functional
            LinQiao(林峤<br/>观察者):::char
        end

        subgraph LivingUnit [生活区]
            direction TB
            School(第四小学):::living
            Home(沈仪家):::living
            ShenYi(沈仪<br/>逃避者):::char
        end
        
        subgraph Industry [工业物流园]
            direction TB
            Station(星速配送站):::functional
            LuoQi(罗启<br/>摆渡人):::char
        end
    end

    subgraph ZoneOld ["旧城区 / Zone Old (SAI > 5.0)"]
        direction TB
        %% 调整顺序以配合连线
        NoodleShop(老街面馆<br/>命运交汇点):::old
        RustAlley(锈巷):::old
        RepairShop(旧家电维修店<br/>底层接口):::old
        JiuDuan(旧端<br/>看守者):::char
    end

    subgraph ZoneWild ["外部荒野 / Zone Wild (SAI N/A)"]
        direction TB
        Excavation(罗布泊遗迹<br/>4.7万年前):::wild
        Echo(回声观测站<br/>暗物质阵列):::wild
        ZhouMan(周曼<br/>聆听者):::char
    end

    %% ==========================================
    %% 布局辅助：(Hidden Links)
    %% ==========================================
    HY0 ~~~ Inst
    LinQiao ~~~ NoodleShop
    NoodleShop ~~~ Excavation

    %% ==========================================
    %% 关系连线 (Relationships & Movements)
    %% ==========================================

    %% 上层动线：林峤跨越旧城直达荒野
    LinQiao <==>|田野调查| Excavation
    LinQiao -.->|寻找噪音| NoodleShop
    
    %% 中层动线：沈仪生活圈
    ShenYi <==>|授课| School
    ShenYi <==>|育儿| Home
    ShenYi -.->|老熟客| NoodleShop

    %% 下层动线：罗启与旧端穿透核心
    LuoQi <==>|配送| LivingUnit
    LuoQi <==>|走私| RustAlley
    Station -.->|物流网络| Home

    JiuDuan ---|驻扎| RepairShop
    RepairShop ---|邻里| NoodleShop
    
    %% 长跨度连线：旧端通向核心（尽量置于底部避免交叉）
    JiuDuan -.->|物理后门| HY0

    %% 边缘监测
    ZhouMan ---|驻扎| Echo
    Echo -.->|捕获异常| Excavation

    %% 核心事件交汇
    Intersect((三人同框))
    NoodleShop == "初次无声交汇<br/>(Chapter 3)" === Intersect
    LinQiao --- Intersect
    ShenYi --- Intersect
    JiuDuan --- Intersect
```
