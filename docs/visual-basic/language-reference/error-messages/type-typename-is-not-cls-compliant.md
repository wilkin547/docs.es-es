---
description: 'Más información sobre: BC40041: el tipo <typename> no es conforme a CLS'
title: El tipo <typename> no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: a1e807dba64f2fce70b0fb39147087d91ca80fbc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99675044"
---
# <a name="bc40041-type-typename-is-not-cls-compliant"></a><span data-ttu-id="38dfb-103">BC40041: el tipo \<typename> no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="38dfb-103">BC40041: Type \<typename> is not CLS-compliant</span></span>

<span data-ttu-id="38dfb-104">Una variable, una propiedad o un valor devuelto por una función se declara con un tipo de datos que no es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="38dfb-104">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>

 <span data-ttu-id="38dfb-105">Para que una aplicación sea compatible con la [independencia del lenguaje y los componentes de Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS), solo debe usar tipos conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="38dfb-105">For an application to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span>

 <span data-ttu-id="38dfb-106">Los siguientes tipos de datos de Visual Basic no son conformes a CLS:</span><span class="sxs-lookup"><span data-stu-id="38dfb-106">The following Visual Basic data types are not CLS-compliant:</span></span>

- [<span data-ttu-id="38dfb-107">Tipo de datos SByte</span><span class="sxs-lookup"><span data-stu-id="38dfb-107">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)

- [<span data-ttu-id="38dfb-108">Tipo de datos UInteger</span><span class="sxs-lookup"><span data-stu-id="38dfb-108">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)

- [<span data-ttu-id="38dfb-109">Tipo de datos ULong</span><span class="sxs-lookup"><span data-stu-id="38dfb-109">ULong Data Type</span></span>](../data-types/ulong-data-type.md)

- [<span data-ttu-id="38dfb-110">Tipo de datos UShort</span><span class="sxs-lookup"><span data-stu-id="38dfb-110">UShort Data Type</span></span>](../data-types/ushort-data-type.md)

 <span data-ttu-id="38dfb-111">**Identificador de error:** BC40041</span><span class="sxs-lookup"><span data-stu-id="38dfb-111">**Error ID:** BC40041</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="38dfb-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="38dfb-112">To correct this error</span></span>

- <span data-ttu-id="38dfb-113">Si la aplicación debe ser conforme a CLS, cambie el tipo de datos de este elemento por el tipo conforme a CLS más próximo.</span><span class="sxs-lookup"><span data-stu-id="38dfb-113">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="38dfb-114">Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="38dfb-114">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="38dfb-115">Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.</span><span class="sxs-lookup"><span data-stu-id="38dfb-115">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>

- <span data-ttu-id="38dfb-116">Si la aplicación no necesita ser conforme a CLS, no es necesario cambiar nada.</span><span class="sxs-lookup"><span data-stu-id="38dfb-116">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="38dfb-117">Sin embargo, debe tener en cuenta su incumplimiento.</span><span class="sxs-lookup"><span data-stu-id="38dfb-117">You should be aware of its noncompliance, however.</span></span>
