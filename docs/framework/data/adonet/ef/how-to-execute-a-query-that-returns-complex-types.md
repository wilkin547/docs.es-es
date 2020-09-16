---
title: Procedimiento para ejecutar una consulta que devuelve tipos complejos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: 01958637cedcd6d502d51e9f0821ff3a9faae840
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545329"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a><span data-ttu-id="081d5-102">Procedimiento para ejecutar una consulta que devuelve tipos complejos</span><span class="sxs-lookup"><span data-stu-id="081d5-102">How to: Execute a Query that Returns Complex Types</span></span>
<span data-ttu-id="081d5-103">En este tema se muestra cómo ejecutar una consulta [!INCLUDE[esql](../../../../../includes/esql-md.md)] que devuelve objetos de tipo entidad que contienen una propiedad de un tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="081d5-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that returns entity type objects that contain a property of a complex type.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="081d5-104">Para ejecutar el código de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="081d5-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="081d5-105">Agregue el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al proyecto y configure el proyecto para usar el Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="081d5-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="081d5-106">Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="081d5-106">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="081d5-107">En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="081d5-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. <span data-ttu-id="081d5-108">Haga doble clic en el archivo. edmx para mostrar el modelo en la [ventana Explorador de modelos](/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) de Entity Designer.</span><span class="sxs-lookup"><span data-stu-id="081d5-108">Double click the .edmx file to display the model in the [Model Browser window](/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) of the Entity Designer.</span></span> <span data-ttu-id="081d5-109">En la superficie de Entity Designer, seleccione `Email` las `Phone` propiedades y del `Contact` tipo de entidad, haga clic con el botón derecho y seleccione **refactorizar en nuevo tipo complejo**.</span><span class="sxs-lookup"><span data-stu-id="081d5-109">On the Entity Designer surface, select the `Email` and `Phone` properties of the `Contact` entity type, then right-click and select **Refactor into New Complex Type**.</span></span>  
  
4. <span data-ttu-id="081d5-110">Un nuevo tipo complejo con las `Email` propiedades y seleccionadas `Phone` se agrega al **Explorador de modelos**.</span><span class="sxs-lookup"><span data-stu-id="081d5-110">A new complex type with the selected `Email` and `Phone` properties is added to the **Model Browser**.</span></span> <span data-ttu-id="081d5-111">Al tipo complejo se le asigna un nombre predeterminado: cambie el nombre del tipo a `EmailPhone` en la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="081d5-111">The complex type is given a default name: rename the type to `EmailPhone` in the **Properties** window.</span></span> <span data-ttu-id="081d5-112">También se agrega una nueva propiedad `ComplexProperty` al tipo de entidad `Contact`.</span><span class="sxs-lookup"><span data-stu-id="081d5-112">Also, a new `ComplexProperty` property is added to the `Contact` entity type.</span></span> <span data-ttu-id="081d5-113">Cambie el nombre de la propiedad a `EmailPhoneComplexType.`.</span><span class="sxs-lookup"><span data-stu-id="081d5-113">Rename the property to `EmailPhoneComplexType.`</span></span>  
  
     <span data-ttu-id="081d5-114">Para obtener información sobre cómo crear y modificar tipos complejos mediante el Asistente para Entity Data Model, vea [Cómo: refactorizar propiedades existentes en una propiedad de tipo complejo](/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) y [Cómo: crear y modificar tipos complejos](/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="081d5-114">For information about creating and modifying complex types by using the Entity Data Model Wizard, see [How to: Refactor Existing Properties into a Complex Type Property](/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) and [How to: Create and Modify Complex Types](/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="081d5-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="081d5-115">Example</span></span>  
 <span data-ttu-id="081d5-116">En el ejemplo siguiente se ejecuta una consulta que devuelve una colección de `Contact` objetos y muestra dos propiedades de los `Contact` objetos: `ContactID` y los valores del `EmailPhoneComplexType` tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="081d5-116">The following example executes a query that returns a collection of `Contact` objects and displays two properties of the `Contact` objects: `ContactID` and the values of the `EmailPhoneComplexType` complex type.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
