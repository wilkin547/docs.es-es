---
title: Definir clases (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- execution [Visual Basic], ending
- objects [Visual Basic], initializing
- Initialize event [Visual Basic]
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9fc173ad853755c4b02a13abc0a80229bebffe64
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-defining-classes-visual-basic"></a>Tutorial: Definir clases (Visual Basic)

Este tutorial muestra cómo definir las clases, que, a continuación, puede usar para crear objetos. También se muestra cómo agregar propiedades y métodos a la nueva clase y se muestra cómo inicializar un objeto.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a>Para definir una clase
  
1.  Cree un proyecto haciendo clic en **nuevo proyecto** en el **archivo** menú. Aparecerá el cuadro de diálogo **Nuevo proyecto** .  
  
2.  Seleccione la aplicación de Windows en la lista de plantillas de proyecto de Visual Basic para mostrar el nuevo proyecto.  
  
3.  Agregue una nueva clase al proyecto, haga clic en **Agregar clase** en el **proyecto** menú. Aparecerá el cuadro de diálogo **Agregar nuevo elemento**.  
  
4.  Seleccione el **clase** plantilla.  
  
5.  La nueva clase el nombre `UserNameInfo.vb`y, a continuación, haga clic en **agregar** para mostrar el código de la nueva clase.  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    >  Puede usar Visual Basic **Editor de código** para agregar una clase al formulario de inicio escribiendo la `Class` palabra clave seguido por el nombre de la nueva clase. El **Editor de código** proporciona correspondiente `End Class` instrucción por usted.  
  
6.  Defina un campo privado para la clase agregando el código siguiente entre las `Class` y `End Class` instrucciones:  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     Declarar el campo como `Private` significa se puede usar solo dentro de la clase. Puede hacer que campos disponibles desde fuera de una clase mediante el uso de modificadores de acceso como `Public` que proporcionan el mayor nivel de acceso. Para obtener más información, consulte [tener acceso a niveles en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
7.  Defina una propiedad para la clase agregando el código siguiente:  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8.  Defina un método para la clase agregando el código siguiente:  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. Definir un constructor con parámetros para la nueva clase agregando un procedimiento denominado `Sub New`:  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     El `Sub New` se llama automáticamente al constructor cuando se crea un objeto basado en esta clase. Este constructor establece el valor del campo que contiene el nombre de usuario.  
  
## <a name="to-create-a-button-to-test-the-class"></a>Para crear un botón para probar la clase
  
1.  Cambia el formulario de inicio al modo de diseño haciendo clic en su nombre en **el Explorador de soluciones** y, a continuación, haga clic en **Diseñador de vistas**. De forma predeterminada, el formulario de inicio para los proyectos de aplicación de Windows se denomina Form1.vb. Aparecerá el formulario principal.  
  
2.  Agregue un botón al formulario principal y haga doble clic para mostrar el código de la `Button1_Click` controlador de eventos. Agregue el siguiente código para llamar al procedimiento de prueba:  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a>Para ejecutar la aplicación
  
1.  Ejecute la aplicación presionando F5. Haga clic en el botón del formulario para llamar al procedimiento de prueba. Muestra un mensaje que indica que el original `UserName` es "Gil, Enrique", porque el procedimiento llamó el `Capitalize` método del objeto.  
  
2.  Haga clic en **Aceptar** para descartar el cuadro de mensaje. El `Button1 Click` procedimiento cambia el valor de la `UserName` propiedad y muestra un mensaje que indica que el nuevo valor de `UserName` es "Worden, Joe".  
  
## <a name="see-also"></a>Vea también

[Programación orientada a objetos (Visual Basic)](../../concepts/object-oriented-programming.md)  
[Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)