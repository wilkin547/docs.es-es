---
title: "El tipo de miembro &#39;&lt;nombre de miembro&gt;&#39; no es compatible con CLS | Microsoft Docs"
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
  - "bc40025"
  - "vbc40025"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40025"
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# El tipo de miembro &#39;&lt;nombre de miembro&gt;&#39; no es compatible con CLS
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El tipo de datos especificado para este miembro no forma parte de [Independencia del lenguaje y componentes independientes del lenguaje](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\).  Éste no es un error de su componente, porque [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] y [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] admiten este tipo de datos.  Sin embargo, es posible que otro componente escrito en código estrictamente conforme a CLS no admita este tipo de datos.  Puede que dicho componente no pueda interactuar correctamente con su componente.  
  
 Los siguientes tipos de datos de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] no son conformes a CLS:  
  
-   [SByte \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 De forma predeterminada, este mensaje es una advertencia.  Para obtener más información sobre cómo ocultar las advertencias o tratar las advertencias como errores, consulte [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40025  
  
### Para corregir este error  
  
-   Si su componente sólo dispone de interfaz con otros componentes de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] o no dispone de interfaz con ningún otro componente, no necesita cambiar nada.  
  
-   Si dispone de interfaz con un componente que no está escrito para [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], puede determinar, mediante la reflexión o la documentación, si admite este tipo de datos.  Si lo hace, no necesita cambiar nada.  
  
-   Si dispone de interfaz con un componente que no admite este tipo de datos, debe reemplazarlo con el tipo conforme a CLS más próximo.  Por ejemplo, si no necesita el intervalo de valores por encima de 2.147.483.647, tal vez pueda utilizar `Integer` en lugar de `UInteger`.  Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.  
  
-   Si crea una interfaz con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen anchos de datos distintos que en [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].  Por ejemplo, `uint` suele ser de 16 bits en otros entornos.  Al pasar un argumento de 16 bits a esos componentes, declárelo como `UShort` en lugar de `UInteger` en el código administrado de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## Vea también  
 [Reflection](../Topic/Reflection%20in%20the%20.NET%20Framework.md)   
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/es-es/4c705105-69a2-4e5e-b24e-0633bc32c7f3)