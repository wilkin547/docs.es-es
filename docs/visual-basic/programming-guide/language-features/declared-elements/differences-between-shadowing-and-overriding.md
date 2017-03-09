---
title: "Diferencias entre sombrear y reemplazar (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "reemplazar, sombrear"
  - "sombrear, reemplazar"
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 24
---
# Diferencias entre sombrear y reemplazar (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Cuando define una clase que hereda de una clase base, a veces desea volver a definir uno o más elementos de la clase base en la clase derivada.  El sombreado y el reemplazo están ambos disponibles para esta finalidad.  
  
## Comparación  
 El sombreado y el reemplazo se utilizan cuando una clase derivada hereda de una clase base y ambos vuelven a definir un elemento declarado con otro.  No obstante, existen diferencias significativas entre ambos.  
  
 La siguiente tabla compara sombrear y reemplazar.  
  
||||  
|-|-|-|  
|Punto de comparación|Sombrear|Reemplazar|  
|Propósito|Protege frente a una modificación posterior de clase base que introduce un miembro ya definido en la clase derivada|Logra el polimorfismo mediante la definición de una implementación distinta de un procedimiento o propiedad con la misma secuencia de llamada<sup>1</sup>|  
|Elemento redefinido|Cualquier tipo de elemento declarado|Sólo un procedimiento \(`Function`, `Sub` o `Operator`\) o propiedad|  
|Elemento de redefinición|Cualquier tipo de elemento declarado|Sólo un procedimiento o propiedad con la secuencia de llamada idéntica<sup>1</sup>|  
|Nivel de acceso de elemento de redefinición|Cualquier nivel de acceso|No se puede cambiar el nivel de acceso de elemento reemplazado|  
|Lectura y escritura de elemento de redefinición|Cualquier combinación|No puede cambiar la capacidad de lectura o de escritura de la propiedad reemplazada|  
|Control sobre redefinición|El elemento de clase base no puede cumplir o prohibir el sombreado|El elemento de clase base puede especificar `MustOverride`, `NotOverridable` u `Overridable`|  
|Utilización de palabras clave|Con las clases derivadas se recomienda el uso de `Shadows`; en caso de que no se especifique `Shadows` ni `Overrides`, se utilizará `Shadows` como predeterminada<sup>2</sup>|En una clase base se requiere `Overridable` o `MustOverride` y en una clase derivada se requiere `Overrides`.|  
|Herencia de elementos de redefinición mediante clases derivadas procedentes de una clase derivada en particular|El elemento de sombreado será heredado por clases derivadas posteriores, mientras que el elemento sombreado permanecerá oculto<sup>3</sup>|El elemento que reemplaza a otro será heredado por clases derivadas posteriores; mientras que el elemento reemplazado permanecerá en el mismo estado.|  
  
 <sup>1</sup> La *secuencia de llamada* se compone de tipo de elemento \(`Function`, `Sub`, `Operator` o `Property`\), nombre, lista de parámetros y tipo de valor devuelto.  No se puede reemplazar un procedimiento con una propiedad o viceversa.  No puede reemplazar un tipo de procedimiento \(`Function`, `Sub` u `Operator`\) con otro tipo.  
  
 <sup>2</sup> si no especifica `Shadows` u `Overrides`, el compilador emite un mensaje de advertencia para ayudarle a asegurarse del tipo de redefinición que desea utilizar.  Si omite la advertencia, se utiliza el mecanismo de sombreado.  
  
 <sup>3</sup> Si el elemento de sombreado no está accesible en una clase derivada posterior, dicho sombreado no se hereda.  Por ejemplo, si se declara como `Private` el elemento de sombreado, cualquier clase que se derive de la clase derivada hereda el elemento original en lugar del elemento de sombreado.  
  
## Instrucciones  
 Normalmente, el reemplazo se utiliza en los casos siguientes:  
  
-   Cuando está definiendo las clases derivadas polimórficas.  
  
-   Cuando quiere tener la seguridad de que el compilador cumpla el tipo de elemento idéntico y la secuencia de llamada.  
  
 Normalmente, el sombreado se utiliza en los casos siguientes:  
  
-   Cuando prevé que se podría modificar su clase base y define un elemento utilizando el mismo nombre que el suyo.  
  
-   Cuando quiere tener la libertad de cambiar el tipo de elemento o la secuencia de llamada.  
  
## Vea también  
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Cómo: Ocultar una variable con el mismo nombre que su variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)   
 [Cómo: Ocultar una variable heredada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)   
 [Cómo: Obtener acceso a una variable que oculta una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)