---
title: "&lt;nombre de miembro&gt; no compatible con CLS no se permite en una interfaz compatible con CLS | Microsoft Docs"
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
  - "bc40033"
  - "vbc40033"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40033"
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;nombre de miembro&gt; no compatible con CLS no se permite en una interfaz compatible con CLS
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una propiedad, procedimiento o evento en una interfaz se marca como `<CLSCompliant(True)>` cuando la propia interfaz está marcada como `<CLSCompliant(False)>` o no está marcada.  
  
 Para que una interfaz cumpla con las especificaciones [Independencia del lenguaje y componentes independientes del lenguaje](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), todos sus miembros deben cumplirlas.  
  
 Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, se establece el parámetro `isCompliant` del atributo en `True` o `False` para indicar compatibilidad o incompatibilidad.  No hay ningún valor predeterminado para este parámetro por lo que debe proporcionar uno.  
  
 Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considerará que no es compatible.  
  
 De forma predeterminada, este mensaje es una advertencia.  Para obtener más información sobre cómo ocultar las advertencias o tratarlas como errores, vea [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40033  
  
### Para corregir este error  
  
-   Si requiere la compatibilidad con CLS y tiene el control sobre el código fuente de interfaz, marque la interfaz como `<CLSCompliant(True)>` si todos sus miembros cumplen sus especificaciones.  
  
-   Si requiere la compatibilidad con CLS y no posee control sobre el código fuente de interfaz, o si éste no cumple los requisitos para ser compatible, defina este miembro dentro de otra interfaz.  
  
-   Si requiere que este miembro permanezca dentro de su interfaz actual, quite el atributo <xref:System.CLSCompliantAttribute> de su definición o márquelo como `<CLSCompliant(False)>`.  
  
## Vea también  
 [Interface \(Instrucción\)](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/es-es/4c705105-69a2-4e5e-b24e-0633bc32c7f3)