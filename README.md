\# CrossApp



Наскрізний проект з крос-платформного програмування.



Предметна область: Замовлення. Сутності: Customer, Product, Order, OrderLine.



Призначення: оформлення замовлень і підрахунок сум.



Структура проєкту

CrossApp/

├── CrossApp.sln

├── README.md

├── .gitignore

└── src/

&#x20;   ├── Core/

&#x20;   │   ├── Core.csproj

&#x20;   │   └── EnvironmentInfo.cs

&#x20;   └── Cli/

&#x20;       ├── Cli.csproj

&#x20;       └── Program.cs



\## Запуск



збірка проєкту

dotnet build

запуск застосунку

dotnet run --project src/Cli



\## Середовище



.NET SDK 10.0, Windows x64



\## Бібліотека Core



це бібліотека класів, яка містить EnvironmentInfo для збору інформації про середовище виконання та EnvironmentReport для зберігання отриманих даних.



Проєкт Cli використовує Core через ProjectReference і відповідає за виведення інформації в консоль.



\## Публікація



Self-contained:

dotnet publish src/Cli -c Release -r win-x64 --self-contained true



Framework-dependent:

dotnet publish src/Cli -c Release -r win-x64 --self-contained false



Порівняння режимів публікації

|RID|Режим|Розмір publish|Потрібен встановлений runtime|
|-|-|-|-|
|win-x64|self-contained|76,85 MB|Ні|
|win-x64|framework-dependent|0,19 MB|Так (.NET 10)|





