---
title: Los parámetros de tipo no se pueden utilizar como calificadores
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 8ee0fd5822c22da090aa0abee679e2f68e0fc1d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659721"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="86342-102">Los parámetros de tipo no se pueden utilizar como calificadores</span><span class="sxs-lookup"><span data-stu-id="86342-102">Type parameters cannot be used as qualifiers</span></span>
<span data-ttu-id="86342-103">Un elemento de programación se califica con una cadena de calificación que incluye un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="86342-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>  
  
 <span data-ttu-id="86342-104">Un parámetro de tipo representa un requisito para un tipo que va a proporcionar al construir el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="86342-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="86342-105">No representa un tipo específico definido.</span><span class="sxs-lookup"><span data-stu-id="86342-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="86342-106">Una cadena de calificación debe incluir solo los elementos que se definen en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="86342-106">A qualification string must include only elements that are defined at compile time.</span></span>  
  
 <span data-ttu-id="86342-107">Las instrucciones siguientes pueden generar este error.</span><span class="sxs-lookup"><span data-stu-id="86342-107">The following statements can generate this error.</span></span>  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 <span data-ttu-id="86342-108">**Identificador de error:** BC32098</span><span class="sxs-lookup"><span data-stu-id="86342-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="86342-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="86342-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="86342-110">Quite el parámetro de tipo de la cadena de calificación o reemplazarlo con un tipo definido.</span><span class="sxs-lookup"><span data-stu-id="86342-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2.  <span data-ttu-id="86342-111">Si necesita utilizar un tipo construido para localizar el elemento de programación que se completa, debe usar la lógica del programa adicionales.</span><span class="sxs-lookup"><span data-stu-id="86342-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86342-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="86342-112">See also</span></span>
- [<span data-ttu-id="86342-113">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="86342-113">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="86342-114">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="86342-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="86342-115">Lista de tipos</span><span class="sxs-lookup"><span data-stu-id="86342-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
