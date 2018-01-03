---
title: "Referencia de ensamblado de confianza &lt;referencia&gt; no es válido"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords: BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ab1c7c5cc7a7f4ad899df7722769238e05d96e6b
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a>Referencia de ensamblado de confianza &lt;referencia&gt; no es válido
Referencia de ensamblado de confianza \<referencia > no es válido. Los ensamblados con signo de nombre seguro deben especificar una clave pública en las declaraciones InternalsVisibleTo.  
  
 El nombre del ensamblado se pasa a la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributo identifica un ensamblado con nombre seguro, pero no incluye un `PublicKey` atributo.  
  
 **Id. de error:** BC31535  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Determinar la clave pública para el ensamblado con nombre seguro friend. Incluya la clave pública como parte del nombre del ensamblado que se pasa a la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributo mediante el uso de la `PublicKey` atributo.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Reflection.AssemblyName>  
 [Ensamblados de confianza](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 

