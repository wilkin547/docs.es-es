---
title: "El nombre &lt;nombre de espacio de nombres&gt; del espacio de nombres ra&#237;z &lt;nombre de espacio completo&gt; no es compatible con CLS | Microsoft Docs"
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
  - "vbc40039"
  - "bc40039"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40039"
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# El nombre &lt;nombre de espacio de nombres&gt; del espacio de nombres ra&#237;z &lt;nombre de espacio completo&gt; no es compatible con CLS
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Un ensamblado está marcado como `<CLSCompliant(True)>`, pero un elemento del nombre de espacio de nombres raíz comienza con un subrayado \(`_`\).  
  
 Un elemento de programación puede contener uno o más caracteres de subrayado, pero para ser compatible con la [Independencia del lenguaje y componentes independientes del lenguaje](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), no debe comenzar con un subrayado.  Vea [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, se establece el parámetro `isCompliant` del atributo en `True` o `False` para indicar compatibilidad o incompatibilidad.  No hay ningún valor predeterminado para este parámetro por lo que debe proporcionar uno.  
  
 Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considerará que no es compatible.  
  
 De forma predeterminada, este mensaje es una advertencia.  Para obtener más información sobre cómo ocultar las advertencias o tratarlas como errores, vea [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40039  
  
### Para corregir este error  
  
-   Si requiere la compatibilidad con CLS, cambie el nombre del espacio de nombres raíz para que ninguno de sus elementos comience con un subrayado.  
  
-   Si requiere que el nombre del espacio de nombres permanezca sin modificar, quite <xref:System.CLSCompliantAttribute> del ensamblado o márquelo como `<CLSCompliant(False)>`.  
  
## Vea también  
 [Namespace \(Instrucción\)](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [\/rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)   
 [Aplicación \(Página, Diseñador de proyectos\) \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)   
 [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/es-es/4c705105-69a2-4e5e-b24e-0633bc32c7f3)