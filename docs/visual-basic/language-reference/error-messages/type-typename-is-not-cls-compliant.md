---
title: El tipo <typename> no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: 243f51b3e6c798c82fdbe7b28557c4f96c728bf2
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55281728"
---
# <a name="type-typename-is-not-cls-compliant"></a><span data-ttu-id="bb8e1-102">Tipo \<typename > no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="bb8e1-102">Type \<typename> is not CLS-compliant</span></span>
<span data-ttu-id="bb8e1-103">Una variable, propiedad o valor devuelto de función se declara con un tipo de datos que no es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="bb8e1-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="bb8e1-104">Para una aplicación sea compatible con la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), debe utilizar solo tipos conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="bb8e1-104">For an application to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="bb8e1-105">Los siguientes tipos de datos de Visual Basic no son conformes a CLS:</span><span class="sxs-lookup"><span data-stu-id="bb8e1-105">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="bb8e1-106">SByte (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="bb8e1-106">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="bb8e1-107">UInteger (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="bb8e1-107">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="bb8e1-108">ULong (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="bb8e1-108">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="bb8e1-109">UShort (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="bb8e1-109">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="bb8e1-110">**Identificador de error:** BC40041</span><span class="sxs-lookup"><span data-stu-id="bb8e1-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bb8e1-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="bb8e1-111">To correct this error</span></span>  
  
-   <span data-ttu-id="bb8e1-112">Si la aplicación debe ser conforme a CLS, cambie el tipo de datos de este elemento para el tipo conforme a CLS más próximo.</span><span class="sxs-lookup"><span data-stu-id="bb8e1-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="bb8e1-113">Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="bb8e1-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="bb8e1-114">Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.</span><span class="sxs-lookup"><span data-stu-id="bb8e1-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="bb8e1-115">Si la aplicación no necesita ser compatible con CLS, no es necesario cambiar nada.</span><span class="sxs-lookup"><span data-stu-id="bb8e1-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="bb8e1-116">Sin embargo debe ser consciente de que no.</span><span class="sxs-lookup"><span data-stu-id="bb8e1-116">You should be aware of its noncompliance, however.</span></span>