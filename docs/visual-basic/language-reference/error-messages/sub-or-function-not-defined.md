---
title: Elemento Sub o Function no definido
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 9eb13d943f9f1cffc984847f7339111e06f5aa6b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373932"
---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="2f0e8-102">Sub o Function no definida (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f0e8-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="2f0e8-103">Se `Sub` `Function` debe definir o para que se llame a.</span><span class="sxs-lookup"><span data-stu-id="2f0e8-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="2f0e8-104">Las causas posibles de este error son:</span><span class="sxs-lookup"><span data-stu-id="2f0e8-104">Possible causes of this error include:</span></span>  
  
- <span data-ttu-id="2f0e8-105">Error al escribir el nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2f0e8-105">Misspelling the procedure name.</span></span>  
  
- <span data-ttu-id="2f0e8-106">Intentar llamar a un procedimiento desde otro proyecto sin agregar explícitamente una referencia a ese proyecto en el cuadro de diálogo **referencias** .</span><span class="sxs-lookup"><span data-stu-id="2f0e8-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
- <span data-ttu-id="2f0e8-107">Especificar un procedimiento que no es visible para el procedimiento que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f0e8-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
- <span data-ttu-id="2f0e8-108">Declarar una rutina de biblioteca de vínculos dinámicos (DLL) de Windows o una rutina de recursos de código de Macintosh que no está en la biblioteca o el recurso de código especificado.</span><span class="sxs-lookup"><span data-stu-id="2f0e8-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2f0e8-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2f0e8-109">To correct this error</span></span>  
  
1. <span data-ttu-id="2f0e8-110">Asegúrese de que el nombre del procedimiento esté escrito correctamente.</span><span class="sxs-lookup"><span data-stu-id="2f0e8-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2. <span data-ttu-id="2f0e8-111">Busque el nombre del proyecto que contiene el procedimiento al que desea llamar en el cuadro de diálogo **referencias** .</span><span class="sxs-lookup"><span data-stu-id="2f0e8-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="2f0e8-112">Si no aparece, haga clic en el botón **examinar** para buscarlo.</span><span class="sxs-lookup"><span data-stu-id="2f0e8-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="2f0e8-113">Active la casilla situada a la izquierda del nombre del proyecto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2f0e8-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="2f0e8-114">Compruebe el nombre de la rutina.</span><span class="sxs-lookup"><span data-stu-id="2f0e8-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f0e8-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2f0e8-115">See also</span></span>

- [<span data-ttu-id="2f0e8-116">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="2f0e8-116">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="2f0e8-117">Administrar referencias en un proyecto</span><span class="sxs-lookup"><span data-stu-id="2f0e8-117">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="2f0e8-118">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="2f0e8-118">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="2f0e8-119">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="2f0e8-119">Function Statement</span></span>](../statements/function-statement.md)
