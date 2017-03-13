---
title: "Palabras clave como nombres de elementos en c&#243;digo (Visual Basic) | Microsoft Docs"
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
  - "nombres de elementos, en el código"
  - "palabras clave [Visual Basic], en el código"
  - "conflictos de nombres"
  - "código de Visual Basic, convenciones de nomenclatura"
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Palabras clave como nombres de elementos en c&#243;digo (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Cualquier elemento de programación \(como una variable, una clase o un miembro\) puede tener el mismo nombre que una palabra clave restringida.  Por ejemplo, puede crear una variable denominada `Loop`.  Sin embargo, para hacer referencia a su versión de la misma \(que tiene el mismo nombre que la palabra clave restringida `Loop`\), debe calificarla precediéndola de su espacio de nombres completo o debe encerrarla entre corchetes \(`[ ]`\), como muestra el ejemplo siguiente.  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 Si no hace ninguna de ellas, Visual Basic de por supuesto el uso de la palabra clave `Loop` intrínseca y produce un error, como en el ejemplo siguiente:  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 Puede utilizar corchetes al hacer referencia a formularios y controles, al declarar una variable o al definir un procedimiento con el mismo nombre que una palabra clave restringida.  Puede resultar sencillo olvidarse de calificar los nombres o de ponerlos entre corchetes, y con ello provocar errores en el código y dificultar su lectura.  Por este motivo, es recomendable que no utilice palabras clave restringidas como nombres de elementos de programa.  Sin embargo, si una futura versión de Visual Basic define una nueva palabra clave que entra en conflicto con un nombre de formulario o de control existente, puede utilizar esta técnica en el momento de actualizar el código para trabajar con la versión nueva.  
  
> [!NOTE]
>  El programa también puede incluir nombres de elementos proporcionados por otros ensamblados a los que se haya hecho referencia.  Si estos nombres están en conflicto con palabras clave restringidas, colocarlos entre corchetes hace que Visual Basic los interprete como elementos definidos por el programador.  
  
## Vea también  
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)