---
title: Procedimiento para defina la cadena de conexión
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: a78158c7553c0b479b935e3b94931313df912c2f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854661"
---
# <a name="how-to-define-the-connection-string"></a>Procedimiento para defina la cadena de conexión

En este tema se muestra cómo definir la cadena de conexión que se usa al conectarse a un modelo conceptual. Este tema se basa en el modelo conceptual de [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) . El modelo AdventureWorks Sales se usa en los temas relacionados con tareas de la documentación de Entity Framework. En este tema se supone que ya ha configurado el Entity Framework y definido el modelo AdventureWorks Sales. Para obtener más información, vea [Cómo: Definir manualmente los archivos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))de asignación y de modelo. Los procedimientos de este tema también se incluyen en [cómo: Configurar manualmente un proyecto](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))de Entity Framework.

> [!NOTE]
> Si usa el Asistente para Entity Data Model en un proyecto de Visual Studio, genera automáticamente un archivo. edmx y configura el proyecto para usar el Entity Framework. Para obtener más información, vea [Cómo: Usar el Asistente para Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))

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

Si el proyecto no tiene un archivo de configuración de la aplicación, puede agregar uno; para ello, seleccione **Agregar nuevo elemento** en el menú **proyecto** , seleccione la categoría **General** , seleccione **archivo de configuración**de la aplicación y, a continuación, haga clic en **Agregar**.

## <a name="see-also"></a>Vea también

- [Inicio rápido](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))
- [Cómo: Crear un nuevo archivo. edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))
- [Herramientas de Entity Data Model de ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
