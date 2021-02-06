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
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="f11a4-103">Procedimiento para defina la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="f11a4-103">How to: Define the Connection String</span></span>

<span data-ttu-id="f11a4-104">En este tema se muestra cómo definir la cadena de conexión que se usa al conectarse a un modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="f11a4-104">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="f11a4-105">Este tema se basa en el modelo conceptual de [AdventureWorks Sales](/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) .</span><span class="sxs-lookup"><span data-stu-id="f11a4-105">This topic is based on the [AdventureWorks Sales](/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) conceptual model.</span></span> <span data-ttu-id="f11a4-106">El modelo AdventureWorks Sales se usa en los temas relacionados con tareas de la documentación de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="f11a4-106">The AdventureWorks Sales Model is used throughout the task-related topics in the Entity Framework documentation.</span></span> <span data-ttu-id="f11a4-107">En este tema se supone que ya ha configurado el Entity Framework y definido el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="f11a4-107">This topic assumes that you have already configured the Entity Framework and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f11a4-108">Para obtener más información, vea [Cómo: definir manualmente los archivos de asignación y de modelo](/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f11a4-108">For more information, see [How to: Manually Define the Model and Mapping Files](/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span></span> <span data-ttu-id="f11a4-109">Los procedimientos de este tema también se incluyen en [Cómo: configurar manualmente un proyecto de Entity Framework](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f11a4-109">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="f11a4-110">Si usa el Asistente para Entity Data Model en un proyecto de Visual Studio, genera automáticamente un archivo. edmx y configura el proyecto para usar el Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="f11a4-110">If you use the Entity Data Model Wizard in a Visual Studio project, it automatically generates an .edmx file and configures the project to use the Entity Framework.</span></span> <span data-ttu-id="f11a4-111">Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f11a4-111">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

## <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="f11a4-112">Para definir la cadena de conexión de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="f11a4-112">To define the Entity Framework connection string</span></span>

- <span data-ttu-id="f11a4-113">Abra el archivo de configuración de la aplicación del proyecto (app.config) y, a continuación, agregue la siguiente cadena de conexión:</span><span class="sxs-lookup"><span data-stu-id="f11a4-113">Open the project's application configuration file (app.config) and add the following connection string:</span></span>

```xml
<connectionStrings>
    <add name="AdventureWorksEntities"
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

<span data-ttu-id="f11a4-114">Si el proyecto no tiene un archivo de configuración de la aplicación, puede agregar uno; para ello, seleccione **Agregar nuevo elemento** en el menú **proyecto** , seleccione la categoría **General** , seleccione **archivo de configuración** de la aplicación y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f11a4-114">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f11a4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f11a4-115">See also</span></span>

- <span data-ttu-id="f11a4-116">[Guía de inicio rápido](/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f11a4-116">[Quickstart](/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span></span>
- <span data-ttu-id="f11a4-117">[Cómo: Crear un nuevo archivo .edmx](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f11a4-117">[How to: Create a New .edmx File](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span></span>
- <span data-ttu-id="f11a4-118">[Herramientas de Entity Data Model de ADO.NET](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f11a4-118">[ADO.NET Entity Data Model  Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
