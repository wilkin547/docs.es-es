---
title: "Tutorial: Crear e implementar interfaces (Visual Basic) | Microsoft Docs"
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
  - "implementación de interfaces, tutorial"
  - "interfaces, crear"
  - "interfaces, pruebas"
  - "interfaces, tutoriales"
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Tutorial: Crear e implementar interfaces (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Las interfaces describen las características de las propiedades, los métodos y los eventos, pero dejan los detalles de la implementación para las estructuras o clases.  
  
 Este tutorial explica cómo declarar e implementar una interfaz.  
  
> [!NOTE]
>  Este tutorial no proporciona información sobre cómo crear una interfaz de usuario.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Para definir una interfaz  
  
1.  Abra un nuevo proyecto de aplicación para Windows de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
2.  Agregue un módulo nuevo al proyecto haciendo clic en **Agregar módulo** en el menú **Proyecto**.  
  
3.  Asigne al módulo el nombre `Module1.vb` y haga clic en **Agregar**.  Aparecerá el código del módulo nuevo.  
  
4.  Defina una interfaz con el nombre `TestInterface` dentro de `Module1`; para ello, escriba `Interface TestInterface` entre las instrucciones `Module` y `End Module` y presione ENTRAR.  El **Editor de código** aplica una sangría delante de la palabra clave `Interface` y agrega una instrucción `End Interface` para formar un bloque de código.  
  
5.  Defina una propiedad, un método y un evento para la interfaz; para ello, sitúe el siguiente código entre las instrucciones `Interface` y `End Interface`:  
  
     [!code-vb[VbVbalrOOP#98](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#98)]  
  
## Implementación  
 Puede notar que la sintaxis utilizada para declarar los miembros de la interfaz es diferente de la sintaxis utilizada para declarar los miembros de la clase.  Esta diferencia refleja el hecho de que las interfaces no pueden contener código de implementación.  
  
#### Para implementar la interfaz  
  
1.  Agregue una clase denominada `ImplementationClass`; para ello, agregue la siguiente instrucción a `Module1` después de la instrucción `End Interface` pero antes de la instrucción `End Module` y, a continuación, presione ENTRAR:  
  
     [!code-vb[VbVbalrOOP#99](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#99)]  
  
     Si está trabajando dentro del entorno de desarrollo integrado, el **Editor de código** proporciona la instrucción `End Class` correspondiente al presionar ENTRAR.  
  
2.  Agregue la siguiente instrucción `Implements` a `ImplementationClass`, que da nombre a la interfaz que implementa la clase:  
  
     [!code-vb[VbVbalrOOP#100](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#100)]  
  
     Cuando se muestra separada de otros elementos en la parte superior de la clase o estructura, la instrucción `Implements` indica que la clase o estructura implementa una interfaz.  
  
     Si está trabajando dentro del entorno de desarrollo integrado, el **Editor de código** implementa los miembros de clase requeridos por `TestInterface` al presionar ENTRAR, y se puede omitir el paso siguiente.  
  
3.  Si no está trabajando dentro del entorno de desarrollo integrado, debe implementar todos los miembros de la interfaz `MyInterface`.  Agregue el código siguiente a `ImplementationClass` para implementar `Event1`, `Method1` y `Prop1`:  
  
     [!code-vb[VbVbalrOOP#101](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#101)]  
  
     La instrucción `Implements` asigna un nombre a la interfaz y al miembro de la interfaz que se está implementando.  
  
4.  Para finalizar la definición de `Prop1`, agregue un campo privado a la clase que almacenó el valor de propiedad:  
  
     [!code-vb[VbVbalrOOP#102](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#102)]  
  
     Devuelva el valor de `pval` desde el descriptor de acceso get de la propiedad.  
  
     [!code-vb[VbVbalrOOP#103](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#103)]  
  
     Establezca el valor de `pval` en el descriptor de acceso set de la propiedad.  
  
     [!code-vb[VbVbalrOOP#104](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#104)]  
  
5.  Para finalizar la definición de `Method1`, agregue el código siguiente:  
  
     [!code-vb[VbVbalrOOP#105](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#105)]  
  
#### Para probar la implementación de la interfaz  
  
1.  Haga clic con el botón secundario del mouse en el formulario de inicio del proyecto en el **Explorador de soluciones** y haga clic en **Ver código**.  El editor mostrará la clase del formulario de inicio.  De manera predeterminada, el formulario de inicio se denomina `Form1`.  
  
2.  Agregue el siguiente campo `testInstance` a la clase `Form1`:  
  
     [!code-vb[VbVbalrOOP#120](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#120)]  
  
     Al declarar `testInstance` como `WithEvents`, la clase `Form1` puede controlar sus eventos.  
  
3.  Agregue el siguiente controlador de eventos a la clase `Form1` para controlar los eventos desencadenados por `testInstance`:  
  
     [!code-vb[VbVbalrOOP#106](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#106)]  
  
4.  Agregue una subrutina denominada `Test` a la clase `Form1` para probar la clase de implementación:  
  
     [!code-vb[VbVbalrOOP#107](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#107)]  
  
     El procedimiento `Test` crea una instancia de la clase que implementa `MyInterface`, asigna esa instancia al campo `testInstance`, define una propiedad y ejecuta un método a través de la interfaz.  
  
5.  Agregue código para llamar al procedimiento `Test` desde el procedimiento `Form1 Load` del formulario de inicio:  
  
     [!code-vb[VbVbalrOOP#108](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#108)]  
  
6.  Ejecute el procedimiento `Test` presionando F5.  Aparecerá el mensaje "Prop1 se ha definido como 9".  Tras hacer clic en Aceptar, aparecerá el mensaje "El parámetro X de Method1 es 5".  Al hacer clic en Aceptar, aparecerá el mensaje "El controlador de eventos ha interceptado el evento".  
  
## Vea también  
 [Implements \(Instrucción\)](../../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Interfaces](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)   
 [Interface \(Instrucción\)](../../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Event \(Instrucción\)](../../../../visual-basic/language-reference/statements/event-statement.md)