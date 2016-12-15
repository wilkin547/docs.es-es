---
title: "&#39;&lt;nombre de elemento&gt;&#39; est&#225; obsoleto (Advertencia de Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc40008"
  - "bc40008"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40008"
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;nombre de elemento&gt;&#39; est&#225; obsoleto (Advertencia de Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una instrucción intenta obtener acceso a un elemento de programación que está marcado con el atributo <xref:System.ObsoleteAttribute> y la directiva para tratarlo como una advertencia.  
  
 Para indicar que un elemento de programación ya no está en uso, puede marcarlo aplicándole <xref:System.ObsoleteAttribute>.  Si hace esto, podrá establecer la propiedad <xref:System.ObsoleteAttribute.IsError%2A> del atributo en `True` o `False`.  Si la establece en `True`, el compilador tratará como un error los intentos de utilizar el elemento.  Si la establece en `False`, o deja el valor predeterminado `False`, el compilador emitirá una advertencia cuando se intente utilizar el elemento.  
  
 De manera predeterminada, este mensaje es una advertencia, pues la propiedad <xref:System.ObsoleteAttribute.IsError%2A> de <xref:System.ObsoleteAttribute> es `False`.  Para obtener más información sobre cómo ocultar las advertencias o tratarlas como errores, vea [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40008  
  
### Para corregir este error  
  
-   Asegúrese de que el nombre del elemento esté escrito correctamente en la referencia del código fuente.  
  
## Vea también  
 [Atributos](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)