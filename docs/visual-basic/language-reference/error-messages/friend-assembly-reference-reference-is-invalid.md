---
title: La referencia de ensamblado de confianza <reference> no es válida
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 796c16e912283d86496a4ccbd3b675ac1433f02d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356408"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a>Referencia de ensamblado de confianza \<referencia > no es válido
Referencia de ensamblado de confianza \<referencia > no es válido. Los ensamblados con signo de nombre seguro deben especificar una clave pública en las declaraciones InternalsVisibleTo.  
  
 El nombre del ensamblado se pasa a la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributo identifica un ensamblado con nombre seguro, pero no incluye un `PublicKey` atributo.  
  
 **Identificador de error:** BC31535  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Determinar la clave pública para el ensamblado de confianza con nombre seguro. Incluya la clave pública como parte del nombre de ensamblado pasado a la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributo utilizando la `PublicKey` atributo.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Reflection.AssemblyName>
- [Ensamblados de confianza](../../../standard/assembly/friend-assemblies.md)


