---
title: La referencia de ensamblado de confianza <reference> no es válida
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 6eb46c6479adc69eaf65b34c69aa69977b4d62ef
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972392"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a>La referencia de \<referencia de ensamblado de confianza > no es válida
La referencia de \<referencia de ensamblado de confianza > no es válida. Los ensamblados con signo de nombre seguro deben especificar una clave pública en las declaraciones InternalsVisibleTo.  
  
 El nombre de ensamblado pasado <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> al constructor de atributos identifica un ensamblado con nombre seguro, pero no incluye `PublicKey` un atributo.  
  
 **IDENTIFICADOR de error:** BC31535  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Determine la clave pública del ensamblado de confianza con nombre seguro. Incluya la clave pública como parte del nombre del ensamblado pasado al <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributo mediante el `PublicKey` atributo.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Reflection.AssemblyName>
- [Ensamblados de confianza](../../../standard/assembly/friend.md)
