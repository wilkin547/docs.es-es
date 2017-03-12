---
title: "La referencia de ensamblado de confianza &lt;referencia&gt; no es v&#225;lida | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc31535"
  - "bc31535"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31535"
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# La referencia de ensamblado de confianza &lt;referencia&gt; no es v&#225;lida
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

La referencia de ensamblado de confianza \<referencia\> no es válida.Los ensamblados firmados con nombre seguro deben especificar una clave pública en sus declaraciones InternalsVisibleTo.  
  
 El nombre de ensamblado pasado al constructor de atributos <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> identifica un ensamblado con nombre seguro, pero no incluye un atributo `PublicKey`.  
  
 **Id. de error:** BC31535  
  
### Para corregir este error  
  
1.  Determine la clave pública para el ensamblado de confianza con nombre seguro.  Incluya la clave pública como parte del nombre de ensamblado pasado al constructor de atributos <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> mediante el atributo `PublicKey`.  
  
## Vea también  
 <xref:System.Reflection.AssemblyName>   
 [Ensamblados de confianza](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Cómo: Crear ensamblados de confianza firmados](../Topic/How%20to:%20Create%20Signed%20Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)