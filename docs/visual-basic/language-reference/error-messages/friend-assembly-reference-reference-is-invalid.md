---
title: La referencia de ensamblado de confianza <reference> no es válida
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: ff2cdbebe13f6224209ef8da62600c99348c911b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286824"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a>Referencia de ensamblado de confianza \<referencia > no es válido
Referencia de ensamblado de confianza \<referencia > no es válido. Los ensamblados con signo de nombre seguro deben especificar una clave pública en las declaraciones InternalsVisibleTo.  
  
 El nombre del ensamblado se pasa a la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributo identifica un ensamblado con nombre seguro, pero no incluye un `PublicKey` atributo.  
  
 **Identificador de error:** BC31535  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Determinar la clave pública para el ensamblado de confianza con nombre seguro. Incluya la clave pública como parte del nombre de ensamblado pasado a la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributo utilizando la `PublicKey` atributo.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Reflection.AssemblyName>
- [Ensamblados de confianza](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)


