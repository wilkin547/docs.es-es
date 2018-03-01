---
title: Sub o Function no definida (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6237ca26b06bdffa06499607e634b3222725c189
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="98250-102">Sub o Function no definida (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98250-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="98250-103">A `Sub` o `Function` deben definirse con el fin de llamar.</span><span class="sxs-lookup"><span data-stu-id="98250-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="98250-104">Las causas posibles de este error son:</span><span class="sxs-lookup"><span data-stu-id="98250-104">Possible causes of this error include:</span></span>  
  
-   <span data-ttu-id="98250-105">Error al escribir el nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="98250-105">Misspelling the procedure name.</span></span>  
  
-   <span data-ttu-id="98250-106">Intenta llamar a un procedimiento desde otro proyecto sin agregar explícitamente una referencia a ese proyecto en el **referencias** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="98250-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
-   <span data-ttu-id="98250-107">Especifica un procedimiento que no es visible para el procedimiento que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="98250-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
-   <span data-ttu-id="98250-108">La declaración de una rutina de biblioteca de vínculos dinámicos (DLL) de Windows o una rutina de recurso de código de Macintosh que no está en el recurso de biblioteca o el código especificado.</span><span class="sxs-lookup"><span data-stu-id="98250-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="98250-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="98250-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="98250-110">Asegúrese de que el nombre del procedimiento se ha escrito correctamente.</span><span class="sxs-lookup"><span data-stu-id="98250-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2.  <span data-ttu-id="98250-111">Busque el nombre del proyecto que contiene el procedimiento que desea llamar el **referencias** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="98250-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="98250-112">Si no aparece, haga clic en el **examinar** botón para buscarlo.</span><span class="sxs-lookup"><span data-stu-id="98250-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="98250-113">Active la casilla situada a la izquierda del nombre del proyecto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="98250-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="98250-114">Compruebe el nombre de la rutina.</span><span class="sxs-lookup"><span data-stu-id="98250-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98250-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="98250-115">See Also</span></span>  
 [<span data-ttu-id="98250-116">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="98250-116">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="98250-117">Administrar referencias en un proyecto</span><span class="sxs-lookup"><span data-stu-id="98250-117">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="98250-118">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="98250-118">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="98250-119">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="98250-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
