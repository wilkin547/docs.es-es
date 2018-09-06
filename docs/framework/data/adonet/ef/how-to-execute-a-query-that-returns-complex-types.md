---
title: 'Cómo: Ejecutar una consulta que devuelve tipos complejos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: 013f1980d2ea13927871719aeea293cfce38b4d5
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861899"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a><span data-ttu-id="45ef9-102">Cómo: Ejecutar una consulta que devuelve tipos complejos</span><span class="sxs-lookup"><span data-stu-id="45ef9-102">How to: Execute a Query that Returns Complex Types</span></span>
<span data-ttu-id="45ef9-103">En este tema se muestra cómo ejecutar una consulta [!INCLUDE[esql](../../../../../includes/esql-md.md)] que devuelve objetos de tipo entidad que contienen una propiedad de un tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="45ef9-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that returns entity type objects that contain a property of a complex type.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="45ef9-104">Para ejecutar el código de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="45ef9-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="45ef9-105">Agregar el [modelo AdventureWorks Sales](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) al proyecto y configurar el proyecto para usar el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45ef9-105">Add the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="45ef9-106">Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="45ef9-106">For more information, see [How to: Use the Entity Data Model Wizard](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="45ef9-107">En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="45ef9-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="45ef9-108">Haga doble clic en el archivo .edmx para mostrar el modelo en el [ventana Explorador de modelos](https://msdn.microsoft.com/library/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd) de Entity Designer.</span><span class="sxs-lookup"><span data-stu-id="45ef9-108">Double click the .edmx file to display the model in the [Model Browser window](https://msdn.microsoft.com/library/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd) of the Entity Designer.</span></span> <span data-ttu-id="45ef9-109">En la superficie de Entity Designer, seleccione el `Email` y `Phone` propiedades de la `Contact` tipo de entidad, a continuación, secundario y seleccione **refactorizar en nuevo tipo complejo**.</span><span class="sxs-lookup"><span data-stu-id="45ef9-109">On the Entity Designer surface, select the `Email` and `Phone` properties of the `Contact` entity type, then right-click and select **Refactor into New Complex Type**.</span></span>  
  
4.  <span data-ttu-id="45ef9-110">Un nuevo tipo complejo con seleccionado `Email` y `Phone` propiedades se agrega a la **Explorador de modelos**.</span><span class="sxs-lookup"><span data-stu-id="45ef9-110">A new complex type with the selected `Email` and `Phone` properties is added to the **Model Browser**.</span></span> <span data-ttu-id="45ef9-111">El tipo complejo se asigna un nombre predeterminado: cambie el tipo a `EmailPhone` en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="45ef9-111">The complex type is given a default name: rename the type to `EmailPhone` in the **Properties** window.</span></span> <span data-ttu-id="45ef9-112">También se agrega una nueva propiedad `ComplexProperty` al tipo de entidad `Contact`.</span><span class="sxs-lookup"><span data-stu-id="45ef9-112">Also, a new `ComplexProperty` property is added to the `Contact` entity type.</span></span> <span data-ttu-id="45ef9-113">Cambie el nombre de la propiedad a `EmailPhoneComplexType.`.</span><span class="sxs-lookup"><span data-stu-id="45ef9-113">Rename the property to `EmailPhoneComplexType.`</span></span>  
  
     <span data-ttu-id="45ef9-114">Para obtener información sobre cómo crear y modificar tipos complejos mediante el Asistente para Entity Data Model, vea [Cómo: refactorizar propiedades existentes en una propiedad de tipo complejo](https://msdn.microsoft.com/library/5b2eb3b3-693d-42cb-b43a-405812d677eb) y [Cómo: crear y modificar tipos complejos](https://msdn.microsoft.com/library/afb8e206-0ffe-4597-b6d4-6ab566897e1d).</span><span class="sxs-lookup"><span data-stu-id="45ef9-114">For information about creating and modifying complex types by using the Entity Data Model Wizard, see [How to: Refactor Existing Properties into a Complex Type Property](https://msdn.microsoft.com/library/5b2eb3b3-693d-42cb-b43a-405812d677eb) and [How to: Create and Modify Complex Types](https://msdn.microsoft.com/library/afb8e206-0ffe-4597-b6d4-6ab566897e1d).</span></span>  
  
## <a name="example"></a><span data-ttu-id="45ef9-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="45ef9-115">Example</span></span>  
 <span data-ttu-id="45ef9-116">En el ejemplo siguiente se ejecuta una consulta que devuelve una colección de `Contact` objetos y muestra dos propiedades de la `Contact` objetos: `ContactID` y los valores de la `EmailPhoneComplexType` tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="45ef9-116">The following example executes a query that returns a collection of `Contact` objects and displays two properties of the `Contact` objects: `ContactID` and the values of the `EmailPhoneComplexType` complex type.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
