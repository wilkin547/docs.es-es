---
title: La excepción del comentario XML debe tener un atributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 54965f3796b6c5ef0e387cd354abcb5740476257
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321173"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="2a6c8-102">La excepción del comentario XML debe tener un atributo 'cref'</span><span class="sxs-lookup"><span data-stu-id="2a6c8-102">XML comment exception must have a 'cref' attribute</span></span>

<span data-ttu-id="2a6c8-103">La etiqueta \<exception > proporciona una manera de documentar las excepciones que puede producir un método.</span><span class="sxs-lookup"><span data-stu-id="2a6c8-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="2a6c8-104">El atributo `cref` necesario designa el nombre de un miembro, que se comprueba en el generador de documentación.</span><span class="sxs-lookup"><span data-stu-id="2a6c8-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="2a6c8-105">Si el miembro existe, se traduce al nombre de elemento canónico en el archivo de documentación.</span><span class="sxs-lookup"><span data-stu-id="2a6c8-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>

<span data-ttu-id="2a6c8-106">**Identificador de error:** BC42319</span><span class="sxs-lookup"><span data-stu-id="2a6c8-106">**Error ID:** BC42319</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="2a6c8-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2a6c8-107">To correct this error</span></span>

<span data-ttu-id="2a6c8-108">Agregue el atributo `cref` a la excepción como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="2a6c8-108">Add the `cref` attribute to the exception as follows:</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a><span data-ttu-id="2a6c8-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a6c8-109">See also</span></span>

- [<span data-ttu-id="2a6c8-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="2a6c8-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [<span data-ttu-id="2a6c8-111">Crear documentación XML</span><span class="sxs-lookup"><span data-stu-id="2a6c8-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="2a6c8-112">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="2a6c8-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
