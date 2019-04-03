---
title: Los parámetros de tipo no se pueden utilizar como calificadores
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 974d2935e64151109b688f576229fb008b59b229
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819806"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="cbf0c-102">Los parámetros de tipo no se pueden utilizar como calificadores</span><span class="sxs-lookup"><span data-stu-id="cbf0c-102">Type parameters cannot be used as qualifiers</span></span>
<span data-ttu-id="cbf0c-103">Un elemento de programación se califica con una cadena de calificación que incluye un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>  
  
 <span data-ttu-id="cbf0c-104">Un parámetro de tipo representa un requisito para un tipo que va a proporcionar al construir el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="cbf0c-105">No representa un tipo específico definido.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="cbf0c-106">Una cadena de calificación debe incluir solo los elementos que se definen en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-106">A qualification string must include only elements that are defined at compile time.</span></span>  
  
 <span data-ttu-id="cbf0c-107">Las instrucciones siguientes pueden generar este error.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-107">The following statements can generate this error.</span></span>  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 <span data-ttu-id="cbf0c-108">**Identificador de error:** BC32098</span><span class="sxs-lookup"><span data-stu-id="cbf0c-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cbf0c-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="cbf0c-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="cbf0c-110">Quite el parámetro de tipo de la cadena de calificación o reemplazarlo con un tipo definido.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2.  <span data-ttu-id="cbf0c-111">Si necesita utilizar un tipo construido para localizar el elemento de programación que se completa, debe usar la lógica del programa adicionales.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbf0c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbf0c-112">See also</span></span>

- [<span data-ttu-id="cbf0c-113">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="cbf0c-113">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="cbf0c-114">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cbf0c-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="cbf0c-115">Lista de tipos</span><span class="sxs-lookup"><span data-stu-id="cbf0c-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
