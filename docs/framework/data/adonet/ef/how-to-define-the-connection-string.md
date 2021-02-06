---
description: 'Más información sobre: Cómo: definir la cadena de conexión'
title: Procedimiento para defina la cadena de conexión
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 104264299e597bc142a689aa83f3207765d18c67
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650825"
---
# <a name="how-to-define-the-connection-string"></a>Procedimiento para defina la cadena de conexión

En este tema se muestra cómo definir la cadena de conexión que se usa al conectarse a un modelo conceptual. Este tema se basa en el modelo conceptual de [AdventureWorks Sales](/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) . El modelo AdventureWorks Sales se usa en los temas relacionados con tareas de la documentación de Entity Framework. En este tema se supone que ya ha configurado el Entity Framework y definido el modelo AdventureWorks Sales. Para obtener más información, vea [Cómo: definir manualmente los archivos de asignación y de modelo](/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)). Los procedimientos de este tema también se incluyen en [Cómo: configurar manualmente un proyecto de Entity Framework](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).

> [!NOTE]
> Si usa el Asistente para Entity Data Model en un proyecto de Visual Studio, genera automáticamente un archivo. edmx y configura el proyecto para usar el Entity Framework. Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).

## <a name="to-define-the-entity-framework-connection-string"></a>Para definir la cadena de conexión de Entity Framework

- Abra el archivo de configuración de la aplicación del proyecto (app.config) y, a continuación, agregue la siguiente cadena de conexión:

```xml
<connectionStrings>
    <add name="AdventureWorksEntities"
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

Si el proyecto no tiene un archivo de configuración de la aplicación, puede agregar uno; para ello, seleccione **Agregar nuevo elemento** en el menú **proyecto** , seleccione la categoría **General** , seleccione **archivo de configuración** de la aplicación y, a continuación, haga clic en **Agregar**.

## <a name="see-also"></a>Vea también

- [Guía de inicio rápido](/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))
- [Cómo: Crear un nuevo archivo .edmx](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))
- [Herramientas de Entity Data Model de ADO.NET](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
