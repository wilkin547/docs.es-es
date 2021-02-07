---
description: "Más información acerca de: BC31194: el valor de tipo ' tipo1 ' no se puede convertir en ' Type2 '"
title: Un valor de tipo 'tipo1' no se puede convertir en 'tipo2'
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 8cdb5206f0bc09a447ce241921b0efda63792c28
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674784"
---
# <a name="bc31194-value-of-type-type1-cannot-be-converted-to-type2"></a><span data-ttu-id="c724d-103">BC31194: el valor de tipo ' tipo1 ' no se puede convertir en ' Type2 '</span><span class="sxs-lookup"><span data-stu-id="c724d-103">BC31194: Value of type 'type1' cannot be converted to 'type2'</span></span>

<span data-ttu-id="c724d-104">El valor de tipo ' tipo1 ' no se puede convertir en ' Type2 '.</span><span class="sxs-lookup"><span data-stu-id="c724d-104">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="c724d-105">Puede usar la propiedad ' value ' para obtener el valor de cadena del primer elemento de ' \<parentElement> '.</span><span class="sxs-lookup"><span data-stu-id="c724d-105">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>

 <span data-ttu-id="c724d-106">Se intentó convertir implícitamente un literal XML a un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="c724d-106">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="c724d-107">El literal XML no se puede convertir implícitamente al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="c724d-107">The XML literal cannot be implicitly cast to the specified type.</span></span>

 <span data-ttu-id="c724d-108">**Identificador de error:** BC31194</span><span class="sxs-lookup"><span data-stu-id="c724d-108">**Error ID:** BC31194</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c724d-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c724d-109">To correct this error</span></span>

- <span data-ttu-id="c724d-110">Use la propiedad `Value` del literal XML para hacer referencia a su valor como `String`.</span><span class="sxs-lookup"><span data-stu-id="c724d-110">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="c724d-111">Use la función `CType` , otra función de conversión de tipo o la clase <xref:System.Convert> para convertir el valor como el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="c724d-111">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>

## <a name="see-also"></a><span data-ttu-id="c724d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c724d-112">See also</span></span>

- <xref:System.Convert>
- [<span data-ttu-id="c724d-113">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="c724d-113">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="c724d-114">Literales XML</span><span class="sxs-lookup"><span data-stu-id="c724d-114">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="c724d-115">XML</span><span class="sxs-lookup"><span data-stu-id="c724d-115">XML</span></span>](../../programming-guide/language-features/xml/index.md)
