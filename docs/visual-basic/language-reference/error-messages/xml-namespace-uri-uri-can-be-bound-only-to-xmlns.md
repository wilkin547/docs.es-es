---
title: El identificador URI de espacio de nombres "<uri>" solo se puede enlazar a "xmlns"
ms.date: 07/20/2015
f1_keywords:
- bc31183
- vbc31183
helpviewer_keywords:
- BC31183
ms.assetid: 0ab1dbce-8397-4959-b2cd-f58798b051a0
ms.openlocfilehash: 1aec6ac0a354bfe7e0378a2e46a70a7161bf6d36
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163251"
---
# <a name="bc31183-xml-namespace-uri-httpwwww3orgxml1998namespace-can-be-bound-only-to-xmlns"></a>BC31183: URI de espacio `http://www.w3.org/XML/1998/namespace` de nombres XML; solo se puede enlazar a ' xmlns '

El URI `http://www.w3.org/XML/1998/namespace` se usa en una declaración de espacio de nombres XML. Este URI es un espacio de nombres reservado y no se puede incluir en una declaración de espacio de nombres XML.

 **Identificador de error:** BC31183

## <a name="to-correct-this-error"></a>Para corregir este error

Quite la declaración de espacio de nombres XML o reemplace el URI `http://www.w3.org/XML/1998/namespace` por un URI de espacio de nombres válido.

## <a name="see-also"></a>Vea también

- [Imports (Instrucción, Espacio de nombres XML)](../statements/imports-statement-xml-namespace.md)
- [Literales XML](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
