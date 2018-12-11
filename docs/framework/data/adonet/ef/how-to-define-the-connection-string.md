---
title: Procedimiento Definir la cadena de conexión
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 7fb722acbb13b3502d004978581701cc70118ff8
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129693"
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="924e3-102">Procedimiento Definir la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="924e3-102">How to: Define the Connection String</span></span>

<span data-ttu-id="924e3-103">En este tema se muestra cómo definir la cadena de conexión que se usa al conectarse a un modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="924e3-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="924e3-104">En este tema se basa en el [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="924e3-104">This topic is based on the [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) conceptual model.</span></span> <span data-ttu-id="924e3-105">El modelo AdventureWorks Sales se usa en todos los temas relacionados con tareas de la documentación de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="924e3-105">The AdventureWorks Sales Model is used throughout the task-related topics in the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] documentation.</span></span> <span data-ttu-id="924e3-106">En este tema se da por supuesto que ya ha configurado la [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] y define el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="924e3-106">This topic assumes that you have already configured the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="924e3-107">Para obtener más información, vea [Cómo: Archivos de asignación y definir el modelo manualmente](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="924e3-107">For more information, see [How to: Manually Define the Model and Mapping Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span></span> <span data-ttu-id="924e3-108">Los procedimientos descritos en este tema también se incluyen en [Cómo: Configurar manualmente un proyecto de Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="924e3-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="924e3-109">Si usas el [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] asistente en un proyecto de Visual Studio genera automáticamente un archivo .edmx y configura el proyecto para usar el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="924e3-109">If you use the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] Wizard in a Visual Studio project, it automatically generates an .edmx file and configures the project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="924e3-110">Para obtener más información, vea [Cómo: Utilice al Asistente para Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="924e3-110">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))</span></span>

## <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="924e3-111">Para definir la cadena de conexión de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="924e3-111">To define the Entity Framework connection string</span></span>

- <span data-ttu-id="924e3-112">Abra el archivo de configuración de la aplicación del proyecto (app.config) y, a continuación, agregue la siguiente cadena de conexión:</span><span class="sxs-lookup"><span data-stu-id="924e3-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>

```xml
<connectionStrings>
    <add name="AdventureWorksEntities" 
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

<span data-ttu-id="924e3-113">Si el proyecto no tiene un archivo de configuración de aplicación, puede agregar uno seleccionando **Agregar nuevo elemento** desde el **proyecto** menú, seleccione el **General** categoría, seleccionar **archivo de configuración de aplicación**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="924e3-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>

## <a name="see-also"></a><span data-ttu-id="924e3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="924e3-114">See also</span></span>

- <span data-ttu-id="924e3-115">[Inicio rápido](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="924e3-115">[Quickstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span></span>
- <span data-ttu-id="924e3-116">[Cómo: Crear un nuevo archivo .edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="924e3-116">[How to: Create a New .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span></span>
- <span data-ttu-id="924e3-117">[Herramientas de Entity Data Model de ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="924e3-117">[ADO.NET Entity Data Model  Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
