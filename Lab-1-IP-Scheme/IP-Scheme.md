# IP Scheme
Собрана топология согласно схеме:

<img width="1273" alt="image" src="https://user-images.githubusercontent.com/116812447/198835504-1fe213ce-cbaf-4283-a56a-c33336ad461c.png">
                                   
 Адресное пространство для Underlay сети распределено следующим образом:   
 10.X.Y.Z/30  
 X - номер ЦОДа   
 Y - номер Spine   
 Z - номер в порядке очереди, первый номер всегда принадлежит Spine
 
| Spine  | Leaf | Network |
| ------------- | ------------- | ----------- |
| Spine 1 - 10.1.1.1  | Leaf 1 - 10.1.1.2  | 10.1.1.0/30 |
| Spine 1 - 10.1.1.5 | Leaf 2 - 10.1.1.6  | 10.1.1.4/30 |
| Spine 1 - 10.1.1.9 | Leaf 3 - 10.1.1.10  | 10.1.1.8/30 |
| Spine 2 - 10.1.2.1  | Leaf 1 - 10.1.2.2  | 10.1.2.0/30 |
| Spine 2 - 10.1.2.5 | Leaf 2 - 10.1.2.6  | 10.1.2.4/30 |
| Spine 2 - 10.1.2.9 | Leaf 3 - 10.1.2.10  | 10.1.2.8/30 |

Резервные сети:  
10.1.2.12/30  
10.1.2.16/30  
10.1.2.20/30  


Адреса для loopback интерфейсов:  
10.10.X.Y  
X: 1 - Underlay, 2 - Overlay  
Y: В порядке очереди  
| Device | Underlay Loopback | Overlay loopback |  
| ------------- | ------------- | ----------- |
| Spine 1  | 10.10.1.1/32  | 10.10.2.1/32 |
| Spine 2 | 10.10.1.2/32  | 10.10.2.2/32 |
| Leaf 1| 10.10.1.3/32  | 10.10.2.3/32 |
| Leaf 2| 10.10.1.4/32  | 10.10.2.4/32 |
| Leaf 3| 10.10.1.5/32  | 10.10.2.5/32 |

Резервные адреса:  
10.10.1.6/32 - 10.10.1.10/32  
10.10.2.6/32 - 10.10.2.10/32
