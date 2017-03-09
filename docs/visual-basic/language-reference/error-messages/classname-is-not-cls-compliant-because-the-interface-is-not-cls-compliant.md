---
title: "La clase &#39;&lt;nombre de clase&gt;&#39; no es compatible con CLS porque la interfaz &#39;&lt;nombre de interfaz&gt;&#39; que implementa tampoco lo es | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc40029"
  - "vbc40029"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40029"
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# La clase &#39;&lt;nombre de clase&gt;&#39; no es compatible con CLS porque la interfaz &#39;&lt;nombre de interfaz&gt;&#39; que implementa tampoco lo es
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una clase o interfaz marcada como `<CLSCompliant(True)>` cuando se deriva de o implementa un tipo marcado como `<CLSCompliant(False)>` o que no está marcado.  
  
 Para que una clase o interfaz sea compatible con la [Independencia del lenguaje y componentes independientes del lenguaje](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), su jerarquía de herencia completa debe ser compatible.  Es decir, cada tipo del que hereda, directamente o indirectamente, debe ser compatible.  De forma similar, si una clase implementa una o más interfaces, todas deben ser compatibles a lo largo de toda su jerarquía de herencia.  
  
 Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, se establece el parámetro `isCompliant` del atributo en `True` o `False` para indicar compatibilidad o incompatibilidad.  No hay ningún valor predeterminado para este parámetro por lo que debe proporcionar uno.  
  
 Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considerará que no es compatible.  
  
 De forma predeterminada, este mensaje es una advertencia.  Para obtener más información sobre cómo ocultar las advertencias o tratarlas como errores, vea [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40029  
  
### Para corregir este error  
  
-   Si requiere la compatibilidad con CLS, defina este tipo dentro de una jerarquía de herencia diferente o de un esquema de implementación distinto.  
  
-   Si necesita que este tipo permanezca dentro de su jerarquía de herencia o esquema de implementación actual, quite <xref:System.CLSCompliantAttribute> de su definición o márquelo como `<CLSCompliant(False)>`.  
  
## Vea también  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/es-es/4c705105-69a2-4e5e-b24e-0633bc32c7f3)