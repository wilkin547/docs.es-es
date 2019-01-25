---
title: Referencia de ensamblado de confianza &lt;referencia&gt; no es válido
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: cdedcc18aa82f6efd8c52cdca5d915d7d78e269f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611935"
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a>Referencia de ensamblado de confianza &lt;referencia&gt; no es válido
Referencia de ensamblado de confianza \<referencia > no es válido. Los ensamblados con signo de nombre seguro deben especificar una clave pública en las declaraciones InternalsVisibleTo.  
  
 El nombre del ensamblado se pasa a la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributo identifica un ensamblado con nombre seguro, pero no incluye un `PublicKey` atributo.  
  
 **Identificador de error:** BC31535  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Determinar la clave pública para el ensamblado de confianza con nombre seguro. Incluya la clave pública como parte del nombre de ensamblado pasado a la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributo utilizando la `PublicKey` atributo.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Reflection.AssemblyName>
- [Ensamblados de confianza](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)


