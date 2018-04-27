---
title: Tipo de &lt;typename&gt; no es compatible con CLS
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 73abc8b055e7eb9d1a4f6917d816cab5b4509f86
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="type-lttypenamegt-is-not-cls-compliant"></a><span data-ttu-id="f29e0-102">Tipo de &lt;typename&gt; no es compatible con CLS</span><span class="sxs-lookup"><span data-stu-id="f29e0-102">Type &lt;typename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="f29e0-103">Una variable, propiedad o valor devuelto de función se declara con un tipo de datos que no es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="f29e0-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="f29e0-104">Para una aplicación sea compatible con la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), debe utilizar solo tipos conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="f29e0-104">For an application to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="f29e0-105">Los siguientes tipos de datos de Visual Basic no son conformes a CLS:</span><span class="sxs-lookup"><span data-stu-id="f29e0-105">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="f29e0-106">SByte (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="f29e0-106">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="f29e0-107">UInteger (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="f29e0-107">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="f29e0-108">ULong (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="f29e0-108">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="f29e0-109">UShort (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="f29e0-109">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="f29e0-110">**Id. de error:** BC40041</span><span class="sxs-lookup"><span data-stu-id="f29e0-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f29e0-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f29e0-111">To correct this error</span></span>  
  
-   <span data-ttu-id="f29e0-112">Si la aplicación debe ser conforme a CLS, cambie el tipo de datos de este elemento al tipo conforme a CLS más próximo.</span><span class="sxs-lookup"><span data-stu-id="f29e0-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="f29e0-113">Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="f29e0-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="f29e0-114">Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.</span><span class="sxs-lookup"><span data-stu-id="f29e0-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="f29e0-115">Si la aplicación no necesita ser conforme con CLS, no es necesario cambiar nada.</span><span class="sxs-lookup"><span data-stu-id="f29e0-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="f29e0-116">Sin embargo debe ser consciente de su incumplimiento.</span><span class="sxs-lookup"><span data-stu-id="f29e0-116">You should be aware of its noncompliance, however.</span></span>