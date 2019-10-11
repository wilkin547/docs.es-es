---
title: Los parámetros de tipo no se pueden utilizar como calificadores
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 3ff4b189539bf119351a94dabadd596c336ac723
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250338"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="cf54b-102">Los parámetros de tipo no se pueden utilizar como calificadores</span><span class="sxs-lookup"><span data-stu-id="cf54b-102">Type parameters cannot be used as qualifiers</span></span>

<span data-ttu-id="cf54b-103">Un elemento de programación está calificado con una cadena de calificación que incluye un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="cf54b-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>

<span data-ttu-id="cf54b-104">Un parámetro de tipo representa un requisito para un tipo que se va a proporcionar cuando se construya el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="cf54b-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="cf54b-105">No representa un tipo definido específico.</span><span class="sxs-lookup"><span data-stu-id="cf54b-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="cf54b-106">Una cadena de calificación debe incluir solo los elementos que se definen en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="cf54b-106">A qualification string must include only elements that are defined at compile time.</span></span>

<span data-ttu-id="cf54b-107">El código siguiente puede generar este error:</span><span class="sxs-lookup"><span data-stu-id="cf54b-107">The following code can generate this error:</span></span>

```vb  
Public Function CheckText(Of c As System.Windows.Forms.Control)(
    badText As String) As Boolean
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.
End Function  
```  
  
 <span data-ttu-id="cf54b-108">**IDENTIFICADOR de error:** BC32098</span><span class="sxs-lookup"><span data-stu-id="cf54b-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cf54b-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="cf54b-109">To correct this error</span></span>  
  
1. <span data-ttu-id="cf54b-110">Quite el parámetro de tipo de la cadena de calificación o reemplácelo por un tipo definido.</span><span class="sxs-lookup"><span data-stu-id="cf54b-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2. <span data-ttu-id="cf54b-111">Si necesita usar un tipo construido para buscar el elemento de programación que se va a calificar, debe usar la lógica de programa adicional.</span><span class="sxs-lookup"><span data-stu-id="cf54b-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf54b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf54b-112">See also</span></span>

- [<span data-ttu-id="cf54b-113">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="cf54b-113">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="cf54b-114">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf54b-114">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="cf54b-115">Lista de tipos</span><span class="sxs-lookup"><span data-stu-id="cf54b-115">Type List</span></span>](../statements/type-list.md)
