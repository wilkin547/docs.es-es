---
title: "Tutorial: Definir clases (Visual Basic) | Microsoft Docs"
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
  - "módulos de clase, tutoriales"
  - "clases [Visual Basic], tutoriales"
  - "código, salir"
  - "ejecución, finalizar"
  - "ejecución, detener"
  - "archivos, cerrar"
  - "Initialize (evento)"
  - "objetos [Visual Basic], crear"
  - "objetos [Visual Basic], inicializar"
  - "finalización del programa"
  - "programas, salir"
  - "Terminate (evento)"
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Tutorial: Definir clases (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Este tutorial muestra cómo definir clases que se pueden utilizar luego para crear objetos.  También muestra cómo agregar propiedades y métodos a las clases nuevas, e indica cómo inicializar un objeto.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Para definir una clase  
  
1.  Cree un proyecto haciendo clic en **Nuevo proyecto** en el menú **Archivo**.  Aparecerá el cuadro de diálogo **Nuevo proyecto**.  
  
2.  Seleccione Aplicación para Windows de la lista de plantillas del proyecto de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] para mostrar el nuevo proyecto.  
  
3.  Agregue una clase nueva al proyecto haciendo clic en **Agregar clase** en el menú **Proyecto**.  Aparecerá el cuadro de diálogo **Agregar nuevo elemento**.  
  
4.  Seleccione la plantilla **Clase**.  
  
5.  Asigne a la nueva clase el nombre `UserNameInfo.vb` y, a continuación, haga clic en **Agregar** para mostrar el código de la nueva clase.  
  
     [!code-vb[VbVbalrOOP#5](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_1.vb)]  
  
    > [!NOTE]
    >  Puede utilizar el **Editor de código** de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] para agregar una clase al formulario de inicio escribiendo la palabra clave `Class` seguida del nombre de la clase nueva.  El **Editor de código** proporciona la instrucción `End Class` correspondiente.  
  
6.  Defina un campo privado para la clase; para ello, agregue el siguiente código entre las instrucciones `Class` y `End Class`:  
  
     [!code-vb[VbVbalrOOP#7](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_2.vb)]  
  
     Declarar el campo como `Private` quiere decir que sólo se puede utilizar dentro de la clase.  Se pueden utilizar modificadores de acceso más amplio, por ejemplo `Public`, para hacer que los campos estén disponibles desde fuera de la clase.  Para obtener más información, vea [Niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
7.  Defina una propiedad para la clase agregando el código siguiente:  
  
     [!code-vb[VbVbalrOOP#8](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_3.vb)]  
  
8.  Defina un método para la clase agregando el código siguiente:  
  
     [!code-vb[VbVbalrOOP#9](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_4.vb)]  
  
9. Defina un constructor parametrizado para la clase nueva agregando un procedimiento denominado `Sub New`:  
  
     [!code-vb[VbVbalrOOP#10](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_5.vb)]  
  
     Cuando se crea un objeto basado en esta clase, se llama al constructor `Sub New` automáticamente.  Este constructor establece el valor del campo que contiene el nombre de usuario.  
  
### Para crear un botón que pruebe la clase  
  
1.  Cambie el formulario de inicio al modo de diseño haciendo clic con el botón secundario del mouse en su nombre desde el **Explorador de soluciones** y, a continuación, haga clic en **Diseñador de vistas**.  De forma predeterminada, el nombre que se asigna al formulario de inicio para los proyectos de aplicación para Windows es Form1.vb.  Aparecerá el formulario principal.  
  
2.  Agregue un botón al formulario principal y haga doble clic en él para mostrar el código del controlador de eventos `Button1_Click`.  Agregue el código siguiente para llamar al procedimiento de prueba:  
  
     [!code-vb[VbVbalrOOP#12](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_6.vb)]  
  
### Para ejecutar la aplicación  
  
1.  Presione F5 para ejecutar la aplicación.  Llame al procedimiento de prueba haciendo clic en el botón del formulario.  Muestra un mensaje que indica que el `UserName` original es "MOORE, BOBBY", porque el procedimiento llamó al método `Capitalize` del objeto.  
  
2.  Haga clic en **Aceptar** para descartar el cuadro de mensaje.  El procedimiento `Button1 Click` cambia el valor de la propiedad `UserName` y muestra un mensaje que indica que el nuevo valor de `UserName` es "Worden, Joe."  
  
## Vea también  
 [Programación orientada a objetos](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)   
 [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)