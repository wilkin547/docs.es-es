---
title: Definir clases (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- execution, ending
- objects [Visual Basic], initializing
- Initialize event
- files, closing
- programs, quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event
- execution, stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: aeaa5c2bb85c1a642da15c6a29546cf065380e27
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-defining-classes-visual-basic"></a>Tutorial: Definir clases (Visual Basic)
Este tutorial muestra cómo definir clases que sirven para crear objetos. También se muestra cómo agregar propiedades y métodos a la nueva clase y se muestra cómo inicializar un objeto.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-define-a-class"></a>Para definir una clase  
  
1.  Cree un proyecto haciendo clic en **nuevo proyecto** en el **archivo** menú. Aparecerá el cuadro de diálogo **Nuevo proyecto** .  
  
2.  Seleccione la aplicación para Windows de la lista de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] plantillas para mostrar el nuevo proyecto proyecto.  
  
3.  Agregue una clase nueva al proyecto haciendo clic en **Agregar clase** en el **proyecto** menú. El **Agregar nuevo elemento** aparece el cuadro de diálogo.  
  
4.  Seleccione el **clase** plantilla.  
  
5.  La nueva clase el nombre `UserNameInfo.vb`y, a continuación, haga clic en **agregar** para mostrar el código de la nueva clase.  
  
     [!code-vb[VbVbalrOOP&#5;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_1.vb)]  
  
    > [!NOTE]
    >  Puede usar el [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] **Editor de código** para agregar una clase al formulario de inicio escribiendo la `Class` (palabra clave), seguido del nombre de la nueva clase. El **Editor de código** proporciona correspondiente `End Class` instrucción para usted.  
  
6.  Defina un campo privado para la clase agregando el código siguiente entre las `Class` y `End Class` instrucciones:  
  
     [!code-vb[VbVbalrOOP&#7;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_2.vb)]  
  
     Declarar el campo como `Private` significa que se puede usar solo dentro de la clase. Puede hacer que campos disponibles desde fuera de una clase mediante los modificadores de acceso como `Public` que proporcionan un acceso más. Para obtener más información, consulte [niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
7.  Defina una propiedad para la clase agregando el código siguiente:  
  
     [!code-vb[VbVbalrOOP Nº&8;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_3.vb)]  
  
8.  Defina un método para la clase agregando el código siguiente:  
  
     [!code-vb[VbVbalrOOP&#9;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_4.vb)]  
  
9. Defina un constructor parametrizado para la nueva clase agregando un procedimiento denominado `Sub New`:  
  
     [!code-vb[VbVbalrOOP&#10;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_5.vb)]  
  
     El `Sub New` se llama automáticamente al constructor cuando se crea un objeto basado en esta clase. Este constructor establece el valor del campo que contiene el nombre de usuario.  
  
### <a name="to-create-a-button-to-test-the-class"></a>Para crear un botón para probar la clase  
  
1.  Cambia el formulario de inicio al modo de diseño haciendo clic en su nombre en **el Explorador de soluciones** y, a continuación, haga clic en **Ver diseñador**. De forma predeterminada, el formulario de inicio para los proyectos de aplicación de Windows se denomina Form1.vb. Aparecerá el formulario principal.  
  
2.  Agregue un botón al formulario principal y haga doble clic para mostrar el código de la `Button1_Click` controlador de eventos. Agregue el siguiente código para llamar al procedimiento de prueba:  
  
     [!code-vb[VbVbalrOOP&#12;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_6.vb)]  
  
### <a name="to-run-your-application"></a>Para ejecutar la aplicación  
  
1.  Ejecute la aplicación presionando F5. Haga clic en el botón en el formulario para llamar al procedimiento de prueba. Muestra un mensaje que indica que el original `UserName` es "MOORE, BOBBY", porque el procedimiento llamó la `Capitalize` método del objeto.  
  
2.  Haga clic en **Aceptar** para descartar el cuadro de mensaje. El `Button1 Click` procedimiento cambia el valor de la `UserName` propiedad y muestra un mensaje que indica que el nuevo valor de `UserName` es "Worden, Joe".  
  
## <a name="see-also"></a>Vea también  
 [Programación orientada a objetos](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)   
 [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)

