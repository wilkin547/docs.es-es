---
description: 'Más información acerca de: BC31535: la referencia de ensamblado de confianza <reference> no es válida'
title: La referencia de ensamblado de confianza <reference> no es válida
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: e3e08edede9bee4710c415a61592857229ea4f35
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796202"
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
