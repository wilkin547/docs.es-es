---
title: Procedimiento para ejecutar una consulta que devuelve tipos complejos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: b08b220e969ad1c400413978c85b2f107d64a688
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854643"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a><span data-ttu-id="3d14d-102">Procedimiento para ejecutar una consulta que devuelve tipos complejos</span><span class="sxs-lookup"><span data-stu-id="3d14d-102">How to: Execute a Query that Returns Complex Types</span></span>
<span data-ttu-id="3d14d-103">En este tema se muestra cómo ejecutar una consulta [!INCLUDE[esql](../../../../../includes/esql-md.md)] que devuelve objetos de tipo entidad que contienen una propiedad de un tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="3d14d-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that returns entity type objects that contain a property of a complex type.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="3d14d-104">Para ejecutar el código de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d14d-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="3d14d-105">Agregue el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al proyecto y configure el proyecto para usar el Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="3d14d-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="3d14d-106">Para obtener más información, consulte [Cómo Use el Asistente para](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="3d14d-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="3d14d-107">En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="3d14d-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. <span data-ttu-id="3d14d-108">Haga doble clic en el archivo. edmx para mostrar el modelo en la [ventana Explorador de modelos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) de Entity Designer.</span><span class="sxs-lookup"><span data-stu-id="3d14d-108">Double click the .edmx file to display the model in the [Model Browser window](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) of the Entity Designer.</span></span> <span data-ttu-id="3d14d-109">En la superficie de Entity Designer, seleccione `Email` las `Phone` propiedades y del `Contact` tipo de entidad, haga clic con el botón derecho y seleccione **refactorizar en nuevo tipo complejo**.</span><span class="sxs-lookup"><span data-stu-id="3d14d-109">On the Entity Designer surface, select the `Email` and `Phone` properties of the `Contact` entity type, then right-click and select **Refactor into New Complex Type**.</span></span>  
  
4. <span data-ttu-id="3d14d-110">Un nuevo tipo complejo con las propiedades `Email` y `Phone` seleccionadas se agrega al **Explorador de modelos**.</span><span class="sxs-lookup"><span data-stu-id="3d14d-110">A new complex type with the selected `Email` and `Phone` properties is added to the **Model Browser**.</span></span> <span data-ttu-id="3d14d-111">Al tipo complejo se le asigna un nombre predeterminado: cambie el nombre del `EmailPhone` tipo a en la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="3d14d-111">The complex type is given a default name: rename the type to `EmailPhone` in the **Properties** window.</span></span> <span data-ttu-id="3d14d-112">También se agrega una nueva propiedad `ComplexProperty` al tipo de entidad `Contact`.</span><span class="sxs-lookup"><span data-stu-id="3d14d-112">Also, a new `ComplexProperty` property is added to the `Contact` entity type.</span></span> <span data-ttu-id="3d14d-113">Cambie el nombre de la propiedad a `EmailPhoneComplexType.`.</span><span class="sxs-lookup"><span data-stu-id="3d14d-113">Rename the property to `EmailPhoneComplexType.`</span></span>  
  
     <span data-ttu-id="3d14d-114">Para obtener información acerca de cómo crear y modificar tipos complejos mediante el Asistente para Entity Data Model [, consulte How to: Refactorice las propiedades existentes en una propiedad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) de tipo complejo y [cómo: Crear y modificar tipos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100))complejos.</span><span class="sxs-lookup"><span data-stu-id="3d14d-114">For information about creating and modifying complex types by using the Entity Data Model Wizard, see [How to: Refactor Existing Properties into a Complex Type Property](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) and [How to: Create and Modify Complex Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d14d-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d14d-115">Example</span></span>  
 <span data-ttu-id="3d14d-116">En el ejemplo siguiente se ejecuta una consulta que devuelve una colección `Contact` de objetos y muestra dos propiedades de `Contact` los objetos `ContactID` : y los valores del `EmailPhoneComplexType` tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="3d14d-116">The following example executes a query that returns a collection of `Contact` objects and displays two properties of the `Contact` objects: `ContactID` and the values of the `EmailPhoneComplexType` complex type.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
