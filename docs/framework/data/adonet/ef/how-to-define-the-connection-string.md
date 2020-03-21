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
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="714a4-102">Cómo: Definir la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="714a4-102">How to: Define the Connection String</span></span>

<span data-ttu-id="714a4-103">En este tema se muestra cómo definir la cadena de conexión que se usa al conectarse a un modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="714a4-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="714a4-104">Este tema se basa en el modelo conceptual [AdventureWorks Sales.](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="714a4-104">This topic is based on the [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) conceptual model.</span></span> <span data-ttu-id="714a4-105">El modelo de ventas AdventureWorks se utiliza en todos los temas relacionados con tareas en la documentación de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="714a4-105">The AdventureWorks Sales Model is used throughout the task-related topics in the Entity Framework documentation.</span></span> <span data-ttu-id="714a4-106">En este tema se supone que ya ha configurado Entity Framework y definido el modelo de ventas de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="714a4-106">This topic assumes that you have already configured the Entity Framework and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="714a4-107">Para obtener más información, consulte [Cómo: Definir manualmente el modelo y](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))los archivos de asignación .</span><span class="sxs-lookup"><span data-stu-id="714a4-107">For more information, see [How to: Manually Define the Model and Mapping Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span></span> <span data-ttu-id="714a4-108">Los procedimientos de este tema también se incluyen en [Cómo: configurar manualmente un proyecto](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))de Entity Framework .</span><span class="sxs-lookup"><span data-stu-id="714a4-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="714a4-109">Si usa el Asistente para Entity Data Model en un proyecto de Visual Studio, genera automáticamente un archivo .edmx y configura el proyecto para usar Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="714a4-109">If you use the Entity Data Model Wizard in a Visual Studio project, it automatically generates an .edmx file and configures the project to use the Entity Framework.</span></span> <span data-ttu-id="714a4-110">Para obtener más información, vea [Cómo: usar el Asistente para Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="714a4-110">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

## <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="714a4-111">Para definir la cadena de conexión de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="714a4-111">To define the Entity Framework connection string</span></span>

- <span data-ttu-id="714a4-112">Abra el archivo de configuración de la aplicación del proyecto (app.config) y, a continuación, agregue la siguiente cadena de conexión:</span><span class="sxs-lookup"><span data-stu-id="714a4-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>

```xml
<connectionStrings>
    <add name="AdventureWorksEntities"
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

<span data-ttu-id="714a4-113">Si el proyecto no tiene un archivo de configuración de aplicación, puede agregar uno seleccionando **Agregar nuevo elemento** en el menú **Proyecto,** seleccionando la categoría **General,** seleccionando Archivo de **configuración**de la aplicación y, a continuación, haciendo clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="714a4-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>

## <a name="see-also"></a><span data-ttu-id="714a4-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="714a4-114">See also</span></span>

- <span data-ttu-id="714a4-115">[Quickstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="714a4-115">[Quickstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span></span>
- <span data-ttu-id="714a4-116">[Cómo: Crear un nuevo archivo .edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="714a4-116">[How to: Create a New .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span></span>
- <span data-ttu-id="714a4-117">[Herramientas de Entity Data Model de ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="714a4-117">[ADO.NET Entity Data Model  Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
