---
title: La referencia de ensamblado de confianza <reference> no es válida
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 72c030d18d5339908c5088e104f6a8ad3e76943b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874101"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a>La referencia de ensamblado de confianza \<reference> no es válida

La referencia de ensamblado de confianza \<reference> no es válida. Los ensamblados con signo de nombre seguro deben especificar una clave pública en las declaraciones InternalsVisibleTo.  
  
 El nombre de ensamblado pasado al <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributos identifica un ensamblado con nombre seguro, pero no incluye un `PublicKey` atributo.  
  
 **Identificador de error:** BC31535  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Determine la clave pública del ensamblado de confianza con nombre seguro. Incluya la clave pública como parte del nombre del ensamblado pasado al <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributo mediante el `PublicKey` atributo.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Reflection.AssemblyName>
- [Ensamblados de confianza](../../../standard/assembly/friend.md)
