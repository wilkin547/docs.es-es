---
title: 'Cómo: Ejecutar un procedimiento almacenado parametrizado usando EntityCommand'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
ms.openlocfilehash: 973a1f3980c979b201b083eed3eb20a64461a3cb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43481552"
---
# <a name="how-to-execute-a-parameterized-stored-procedure-using-entitycommand"></a><span data-ttu-id="1b297-102">Cómo: Ejecutar un procedimiento almacenado parametrizado usando EntityCommand</span><span class="sxs-lookup"><span data-stu-id="1b297-102">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>
<span data-ttu-id="1b297-103">En este tema se muestra cómo ejecutar un procedimiento almacenado parametrizado usando la clase <xref:System.Data.EntityClient.EntityCommand>.</span><span class="sxs-lookup"><span data-stu-id="1b297-103">This topic shows how to execute a parameterized stored procedure by using the <xref:System.Data.EntityClient.EntityCommand> class.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="1b297-104">Para ejecutar el código de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b297-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="1b297-105">Agregar el [modelo School](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) al proyecto y configurar el proyecto para usar el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b297-105">Add the [School Model](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="1b297-106">Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="1b297-106">For more information, see [How to: Use the Entity Data Model Wizard](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="1b297-107">En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="1b297-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="1b297-108">Importe el procedimiento almacenado `GetStudentGrades` y especifique entidades `CourseGrade` como tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="1b297-108">Import the `GetStudentGrades` stored procedure and specify `CourseGrade` entities as a return type.</span></span> <span data-ttu-id="1b297-109">Para obtener información sobre cómo importar un procedimiento almacenado, vea [Cómo: importar un procedimiento almacenado](https://msdn.microsoft.com/library/24e68bf4-bd6d-428d-bc35-92d7b8e3736d).</span><span class="sxs-lookup"><span data-stu-id="1b297-109">For information on how to import a stored procedure, see [How to: Import a Stored Procedure](https://msdn.microsoft.com/library/24e68bf4-bd6d-428d-bc35-92d7b8e3736d).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b297-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b297-110">Example</span></span>  
 <span data-ttu-id="1b297-111">El código siguiente ejecuta el procedimiento almacenado `GetStudentGrades` donde `StudentId` es un parámetro necesario.</span><span class="sxs-lookup"><span data-stu-id="1b297-111">The following code executes the `GetStudentGrades` stored procedure where `StudentId` is a required parameter.</span></span> <span data-ttu-id="1b297-112">Los resultados los lee después una clase <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="1b297-112">The results are then read by an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="1b297-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b297-113">See Also</span></span>  
 [<span data-ttu-id="1b297-114">Proveedor de EntityClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="1b297-114">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
