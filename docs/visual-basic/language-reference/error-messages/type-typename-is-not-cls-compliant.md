---
title: "El tipo &lt;nombre de tipo&gt; no es compatible con CLS | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc40041"
  - "vbc40041"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40041"
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# El tipo &lt;nombre de tipo&gt; no es compatible con CLS
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una variable, propiedad o devolución de función está declarada con un tipo de datos que no es conforme a CLS.  
  
 Para que una aplicación sea compatible con [Independencia del lenguaje y componentes independientes del lenguaje](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), debe utilizar sólo tipos conformes a CLS.  
  
 Los siguientes tipos de datos de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] no son conformes a CLS:  
  
-   [SByte \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 **Identificador de error:** BC40041  
  
### Para corregir este error  
  
-   Si su aplicación necesita ser conforme a CLS, cambie el tipo de datos de este elemento por el tipo conforme a CLS más similar.  Por ejemplo, si no necesita el intervalo de valores por encima de 2.147.483.647, tal vez pueda utilizar `Integer` en lugar de `UInteger`.  Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.  
  
-   Si su aplicación no necesita ser conforme a CLS, no es necesario cambiar nada.  Sin embargo, debe estar al tanto de que no es compatible.  
  
## Vea también  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/es-es/4c705105-69a2-4e5e-b24e-0633bc32c7f3)