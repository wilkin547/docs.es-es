---
title: 'Cómo: Definir la cadena de conexión'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: e5b675a50f883825cce97275048447b79b64cc97
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150576"
---
# <a name="how-to-define-the-connection-string"></a>Cómo: Definir la cadena de conexión

En este tema se muestra cómo definir la cadena de conexión que se usa al conectarse a un modelo conceptual. Este tema se basa en el modelo conceptual [AdventureWorks Sales.](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) El modelo de ventas AdventureWorks se utiliza en todos los temas relacionados con tareas en la documentación de Entity Framework. En este tema se supone que ya ha configurado Entity Framework y definido el modelo de ventas de AdventureWorks. Para obtener más información, consulte [Cómo: Definir manualmente el modelo y](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))los archivos de asignación . Los procedimientos de este tema también se incluyen en [Cómo: configurar manualmente un proyecto](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))de Entity Framework .

> [!NOTE]
> Si usa el Asistente para Entity Data Model en un proyecto de Visual Studio, genera automáticamente un archivo .edmx y configura el proyecto para usar Entity Framework. Para obtener más información, vea [Cómo: usar el Asistente para Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).

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

Si el proyecto no tiene un archivo de configuración de aplicación, puede agregar uno seleccionando **Agregar nuevo elemento** en el menú **Proyecto,** seleccionando la categoría **General,** seleccionando Archivo de **configuración**de la aplicación y, a continuación, haciendo clic en **Agregar**.

## <a name="see-also"></a>Consulte también

- [Quickstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))
- [Cómo: Crear un nuevo archivo .edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))
- [Herramientas de Entity Data Model de ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
