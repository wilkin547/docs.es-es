---
title: "C&#243;mo: Obtener acceso a los miembros de un objeto (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "miembros, obtener acceso"
  - "variables de objeto, obtener acceso a miembros"
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Obtener acceso a los miembros de un objeto (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Cuando tiene una variable de objeto que hace referencia a un objeto, a menudo quiere trabajar con los miembros de ese objeto, como métodos, propiedades, campos y eventos.  Por ejemplo, una vez haya creado un nuevo objeto <xref:System.Windows.Forms.Form>, podría querer establecer la propiedad <xref:System.Windows.Forms.Control.Text%2A> o llamar al método <xref:System.Windows.Forms.Control.Focus%2A>.  
  
## Tener acceso a miembros  
 Tiene acceso a los miembros de un objeto a través de la variable que hace referencia a él.  
  
#### Para tener acceso a los miembros de un objeto  
  
-   Utilice el operador de acceso a miembros \(`.`\) entre el nombre de la variable de objeto y el nombre del miembro.  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     Si el miembro es [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), no necesita una variable para tener acceso a él.  
  
## Tener acceso a miembros de un objeto de tipo conocido  
 Si conoce el tipo de un objeto en tiempo de compilación, puede utilizar el *enlace en tiempo de compilación* para una variable que hace referencia a él.  
  
#### Para tener acceso a los miembros de un objeto para el que conoce el tipo en tiempo de compilación  
  
1.  Declare la variable de objeto para que sea del tipo del objeto que piensa asignar a la variable.  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form   
    ```  
  
     Con `Option Strict On`, puede asignar sólo objetos <xref:System.Windows.Forms.Form> \(u objetos de un tipo derivado de <xref:System.Windows.Forms.Form>\)  a `extraForm`.  Si ha definido una clase o estructura con una conversión de ampliación `CType` en <xref:System.Windows.Forms.Form>, también puede asignar esa clase o estructura a `extraForm`.  
  
2.  Utilice el operador de acceso a miembros \(`.`\) entre el nombre de la variable de objeto y el nombre del miembro.  
  
    ```  
    extraForm.Show()  
    ```  
  
     Puede tener acceso a todos los métodos y propiedades específicos de la clase <xref:System.Windows.Forms.Form>, independientemente de cuál sea la configuración de `Option Strict`.  
  
## Tener acceso a miembros de un objeto de tipo desconocido  
 Si no conoce el tipo de un objeto en tiempo de compilación, debe utilizar el *enlace en tiempo de ejecución* para una variable que hace referencia a él.  
  
#### Para tener acceso a los miembros de un objeto para el que no conoce el tipo en tiempo de compilación  
  
1.  Declare la variable de objeto para que sea [Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md).  \(Declarar una variable como `Object` es lo mismo que declararla como <xref:System.Object?displayProperty=fullName>.\)  
  
    ```  
    Dim someControl As Object   
    ```  
  
     Con `Option Strict On`, puede tener acceso sólo a miembros que están definidos en la clase <xref:System.Object>.  
  
2.  Utilice el operador de acceso a miembros \(`.`\) entre el nombre de la variable de objeto y el nombre del miembro.  
  
    ```  
    someControl.GetType()  
    ```  
  
     Para poder tener acceso a miembros de cualquier objeto que asigne a la variable de objeto, debe establecer `Option Strict Off`.  Cuando hace esto, el compilador no puede garantizar que el objeto que asigna a la variable exponga un miembro determinado.  Si el objeto no expone un miembro al que intenta tener acceso, se produce una excepción <xref:System.MemberAccessException>.  
  
## Vea también  
 <xref:System.Object>   
 <xref:System.Windows.Forms.Form>   
 <xref:System.MemberAccessException>   
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)