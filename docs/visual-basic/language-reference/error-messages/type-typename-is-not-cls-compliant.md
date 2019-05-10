---
title: El tipo <typename> no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: 4adbf38e448dad7634a4336d20b3fce8702be1db
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664270"
---
# <a name="type-typename-is-not-cls-compliant"></a><span data-ttu-id="cfc2d-102">Tipo \<typename > no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="cfc2d-102">Type \<typename> is not CLS-compliant</span></span>
<span data-ttu-id="cfc2d-103">Una variable, propiedad o valor devuelto de función se declara con un tipo de datos que no es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="cfc2d-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="cfc2d-104">Para una aplicación sea compatible con la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), debe utilizar solo tipos conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="cfc2d-104">For an application to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="cfc2d-105">Los siguientes tipos de datos de Visual Basic no son conformes a CLS:</span><span class="sxs-lookup"><span data-stu-id="cfc2d-105">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="cfc2d-106">SByte (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="cfc2d-106">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="cfc2d-107">UInteger (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="cfc2d-107">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="cfc2d-108">ULong (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="cfc2d-108">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="cfc2d-109">UShort (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="cfc2d-109">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="cfc2d-110">**Identificador de error:** BC40041</span><span class="sxs-lookup"><span data-stu-id="cfc2d-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cfc2d-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="cfc2d-111">To correct this error</span></span>  
  
- <span data-ttu-id="cfc2d-112">Si la aplicación debe ser conforme a CLS, cambie el tipo de datos de este elemento para el tipo conforme a CLS más próximo.</span><span class="sxs-lookup"><span data-stu-id="cfc2d-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="cfc2d-113">Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="cfc2d-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="cfc2d-114">Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.</span><span class="sxs-lookup"><span data-stu-id="cfc2d-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="cfc2d-115">Si la aplicación no necesita ser compatible con CLS, no es necesario cambiar nada.</span><span class="sxs-lookup"><span data-stu-id="cfc2d-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="cfc2d-116">Sin embargo debe ser consciente de que no.</span><span class="sxs-lookup"><span data-stu-id="cfc2d-116">You should be aware of its noncompliance, however.</span></span>