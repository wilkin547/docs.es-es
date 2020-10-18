---
title: La excepción del comentario XML debe tener un atributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 18e7aa5f6905eaa9c509aa21fe6f5bfcd54d46f0
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163303"
---
# <a name="bc42319-xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="698c3-102">BC42319: la excepción de comentario XML debe tener un atributo ' CREF '</span><span class="sxs-lookup"><span data-stu-id="698c3-102">BC42319: XML comment exception must have a 'cref' attribute</span></span>

<span data-ttu-id="698c3-103">La \<exception> etiqueta proporciona una manera de documentar las excepciones que puede producir un método.</span><span class="sxs-lookup"><span data-stu-id="698c3-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="698c3-104">El atributo required `cref` designa el nombre de un miembro, que está protegido por el generador de documentación.</span><span class="sxs-lookup"><span data-stu-id="698c3-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="698c3-105">Si el miembro existe, se traduce al nombre de elemento canónico en el archivo de documentación.</span><span class="sxs-lookup"><span data-stu-id="698c3-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>

<span data-ttu-id="698c3-106">**Identificador de error:** BC42319</span><span class="sxs-lookup"><span data-stu-id="698c3-106">**Error ID:** BC42319</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="698c3-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="698c3-107">To correct this error</span></span>

<span data-ttu-id="698c3-108">Agregue el `cref` atributo a la excepción como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="698c3-108">Add the `cref` attribute to the exception as follows:</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a><span data-ttu-id="698c3-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="698c3-109">See also</span></span>

- [\<exception>](../xmldoc/exception.md)
- [<span data-ttu-id="698c3-110">Procedimiento para crear documentación XML</span><span class="sxs-lookup"><span data-stu-id="698c3-110">How to: Create XML Documentation</span></span>](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="698c3-111">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="698c3-111">XML Comment Tags</span></span>](../xmldoc/index.md)
