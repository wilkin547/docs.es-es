---
description: "Más información sobre: BC42319: la excepción de comentario XML debe tener un atributo ' CREF '"
title: La excepción del comentario XML debe tener un atributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: e602a2973d95f70d5ab532e6be319a9575d239a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701461"
---
# <a name="bc42319-xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="3077d-103">BC42319: la excepción de comentario XML debe tener un atributo ' CREF '</span><span class="sxs-lookup"><span data-stu-id="3077d-103">BC42319: XML comment exception must have a 'cref' attribute</span></span>

<span data-ttu-id="3077d-104">La \<exception> etiqueta proporciona una manera de documentar las excepciones que puede producir un método.</span><span class="sxs-lookup"><span data-stu-id="3077d-104">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="3077d-105">El atributo required `cref` designa el nombre de un miembro, que está protegido por el generador de documentación.</span><span class="sxs-lookup"><span data-stu-id="3077d-105">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="3077d-106">Si el miembro existe, se traduce al nombre de elemento canónico en el archivo de documentación.</span><span class="sxs-lookup"><span data-stu-id="3077d-106">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>

<span data-ttu-id="3077d-107">**Identificador de error:** BC42319</span><span class="sxs-lookup"><span data-stu-id="3077d-107">**Error ID:** BC42319</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="3077d-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="3077d-108">To correct this error</span></span>

<span data-ttu-id="3077d-109">Agregue el `cref` atributo a la excepción como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="3077d-109">Add the `cref` attribute to the exception as follows:</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a><span data-ttu-id="3077d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="3077d-110">See also</span></span>

- [\<exception>](../xmldoc/exception.md)
- [<span data-ttu-id="3077d-111">Procedimiento para crear documentación XML</span><span class="sxs-lookup"><span data-stu-id="3077d-111">How to: Create XML Documentation</span></span>](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="3077d-112">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="3077d-112">XML Comment Tags</span></span>](../xmldoc/index.md)
