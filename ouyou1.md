```uml
@startuml
start
:weather=天気情報;

if(weather=0)then(true)
:"快晴です"と表示;
elseif(weather=2)then(true)
:"雨です"と表示;
else(false)
:"不明です"と表示;
endif

end
@enduml
```
