---
title: No se admiten referencias de entidad XML
ms.date: 07/20/2015
f1_keywords:
- vbc31180
- bc31180
helpviewer_keywords:
- BC31180
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
ms.openlocfilehash: 37e72dbd6de61a50b4192a0151db40cb4be49d1c
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163277"
---
# <a name="bc31180-xml-entity-references-are-not-supported"></a><span data-ttu-id="4805f-102">BC31180: no se admiten referencias de entidad XML</span><span class="sxs-lookup"><span data-stu-id="4805f-102">BC31180: XML entity references are not supported</span></span>

<span data-ttu-id="4805f-103">Una referencia de entidad (por ejemplo, `©` ) que no se define en la especificación xml 1,0 se incluye como un valor para un literal XML.</span><span class="sxs-lookup"><span data-stu-id="4805f-103">An entity reference (for example, `©`) that is not defined in the XML 1.0 specification is included as a value for an XML literal.</span></span> <span data-ttu-id="4805f-104">Solo `&` `"` `<` `>` `'` se admiten las referencias de entidad XML,,, y en los literales XML.</span><span class="sxs-lookup"><span data-stu-id="4805f-104">Only `&`, `"`, `<`, `>`, and `'` XML entity references are supported in XML literals.</span></span>

 <span data-ttu-id="4805f-105">**Identificador de error:** BC31180</span><span class="sxs-lookup"><span data-stu-id="4805f-105">**Error ID:** BC31180</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="4805f-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="4805f-106">To correct this error</span></span>

- <span data-ttu-id="4805f-107">Quite la referencia de entidad no admitida.</span><span class="sxs-lookup"><span data-stu-id="4805f-107">Remove the unsupported entity reference.</span></span>

## <a name="see-also"></a><span data-ttu-id="4805f-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="4805f-108">See also</span></span>

- [<span data-ttu-id="4805f-109">Literales XML y la especificación XML 1.0</span><span class="sxs-lookup"><span data-stu-id="4805f-109">XML Literals and the XML 1.0 Specification</span></span>](../../programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)
- [<span data-ttu-id="4805f-110">Literales XML</span><span class="sxs-lookup"><span data-stu-id="4805f-110">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="4805f-111">XML</span><span class="sxs-lookup"><span data-stu-id="4805f-111">XML</span></span>](../../programming-guide/language-features/xml/index.md)
