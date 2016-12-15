---
title: "&lt;firma de procedimiento 1&gt; no es compatible con CLS porque sobrecarga a &lt;firma de procedimiento 2&gt; que difiere de ella s&#243;lo en la matriz de tipos de par&#225;metro de matriz o en el rango de los tipos de par&#225;metro de matriz | Microsoft Docs"
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
  - "vbc40035"
  - "bc40035"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40035"
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;firma de procedimiento 1&gt; no es compatible con CLS porque sobrecarga a &lt;firma de procedimiento 2&gt; que difiere de ella s&#243;lo en la matriz de tipos de par&#225;metro de matriz o en el rango de los tipos de par&#225;metro de matriz
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Un procedimiento o propiedad se marca como `<CLSCompliant(True)>` cuando reemplaza otro procedimiento o propiedad y la única diferencia entre sus listas de parámetros es el nivel de anidación de una matriz escalonada o el rango de una matriz.  
  
 En las declaraciones siguientes, la segunda y tercera declaraciones generan este error.  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 La segunda declaración cambia el parámetro unidimensional original `arrayParam` a una matriz de matrices.  La tercera declaración cambia `arrayParam` a una matriz bidimensional \(rango 2\).  Aunque Visual Basic permite que las sobrecargas sólo se diferencien por uno de estos cambios, tal sobrecarga no es compatible con [Independencia del lenguaje y componentes independientes del lenguaje](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\).  
  
 Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, se establece el parámetro `isCompliant` del atributo en `True` o `False` para indicar compatibilidad o incompatibilidad.  No hay ningún valor predeterminado para este parámetro por lo que debe proporcionar uno.  
  
 Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considerará que no es compatible.  
  
 De forma predeterminada, este mensaje es una advertencia.  Para obtener más información sobre cómo ocultar las advertencias o tratarlas como errores, vea [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40035  
  
### Para corregir este error  
  
-   Si requiere compatibilidad con CLS, defina sus sobrecargas para que se diferencien entre sí en más aspectos que únicamente en los cambios citados en esta página de Ayuda.  
  
-   Si requiere que las sobrecargas sólo se diferencien por los cambios indicados en esta página de Ayuda, quite el atributo <xref:System.CLSCompliantAttribute> de sus definiciones o márquelas como `<CLSCompliant(False)>`.  
  
## Vea también  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/es-es/4c705105-69a2-4e5e-b24e-0633bc32c7f3)   
 [Sobrecarga de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)