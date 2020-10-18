---
title: La referencia de ensamblado de confianza <reference> no es válida
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: a42dd99ffaa06dce4823ce5d022fac02ae99c6bd
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160716"
---
# <a name="bc31535-friend-assembly-reference-reference-is-invalid"></a>BC31535: la referencia de ensamblado de confianza \<reference> no es válida

La referencia de ensamblado de confianza \<reference> no es válida. Los ensamblados con signo de nombre seguro deben especificar una clave pública en las declaraciones InternalsVisibleTo.

 El nombre de ensamblado pasado al <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributos identifica un ensamblado con nombre seguro, pero no incluye un `PublicKey` atributo.

 **Identificador de error:** BC31535

## <a name="to-correct-this-error"></a>Para corregir este error

1. Determine la clave pública del ensamblado de confianza con nombre seguro. Incluya la clave pública como parte del nombre del ensamblado pasado al <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributo mediante el `PublicKey` atributo.

## <a name="see-also"></a>Vea también

- <xref:System.Reflection.AssemblyName>
- [Ensamblados de confianza](../../../standard/assembly/friend.md)
