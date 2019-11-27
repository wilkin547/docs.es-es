---
title: Definir clases
ms.date: 07/20/2015
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
ms.openlocfilehash: bd3f6e5cff41551240d9904ab93af8758eb104d2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346082"
---
# <a name="walkthrough-defining-classes-visual-basic"></a>Tutorial: Definir clases (Visual Basic)

En este tutorial se muestra cómo definir clases, que puede usar para crear objetos. También se muestra cómo agregar propiedades y métodos a la nueva clase y se muestra cómo inicializar un objeto.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a>Para definir una clase
  
1. Cree un proyecto haciendo clic en **nuevo proyecto** en el menú **archivo** . Aparece el cuadro de diálogo **Nuevo proyecto**.  
  
2. Seleccione aplicación de Windows en la lista de Visual Basic plantillas de proyecto para mostrar el nuevo proyecto.  
  
3. Agregue una nueva clase al proyecto haciendo clic en **Agregar clase** en el menú **proyecto** . Aparecerá el cuadro de diálogo **Agregar nuevo elemento**.  
  
4. Seleccione la plantilla **clase** .  
  
5. Asigne a la nueva clase el nombre `UserNameInfo.vb`y, a continuación, haga clic en **Agregar** para mostrar el código de la nueva clase.  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    > Puede usar el editor de **código** de Visual Basic para agregar una clase al formulario de inicio escribiendo la palabra clave `Class` seguida del nombre de la nueva clase. El **Editor de código** proporciona una instrucción de `End Class` correspondiente.  
  
6. Defina un campo privado para la clase agregando el código siguiente entre las instrucciones `Class` y `End Class`:  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     Declarar el campo como `Private` significa que solo se puede usar dentro de la clase. Puede hacer que los campos estén disponibles desde fuera de una clase mediante modificadores de acceso como `Public` que proporcionan más acceso. Para obtener más información, consulte [niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
7. Defina una propiedad para la clase agregando el código siguiente:  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8. Defina un método para la clase agregando el código siguiente:  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. Defina un constructor con parámetros para la nueva clase agregando un procedimiento denominado `Sub New`:  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     Se llama al constructor `Sub New` automáticamente cuando se crea un objeto basado en esta clase. Este constructor establece el valor del campo que contiene el nombre de usuario.  
  
## <a name="to-create-a-button-to-test-the-class"></a>Para crear un botón para probar la clase
  
1. Cambie el formulario de inicio al modo de diseño; para ello, haga clic con el botón secundario en su nombre en **Explorador de soluciones** y, a continuación, haga clic en **Ver diseñador**. De forma predeterminada, el formulario de inicio para los proyectos de aplicación de Windows se denomina Form1. VB. Aparecerá el formulario principal.  
  
2. Agregue un botón al formulario principal y haga doble clic en él para mostrar el código del controlador de eventos `Button1_Click`. Agregue el código siguiente para llamar al procedimiento de prueba:  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a>Para ejecutar la aplicación
  
1. Presione F5 para ejecutar la aplicación. Haga clic en el botón del formulario para llamar al procedimiento de prueba. Muestra un mensaje que indica que el `UserName` original es "MOORE, Alberto", porque el procedimiento llamó al método `Capitalize` del objeto.  
  
2. Haga clic en **Aceptar** para descartar el cuadro de mensaje. El procedimiento `Button1 Click` cambia el valor de la propiedad `UserName` y muestra un mensaje que indica que el nuevo valor de `UserName` es "Worden", Joe ".  
  
## <a name="see-also"></a>Vea también

- [Programación orientada a objetos (Visual Basic)](../../concepts/object-oriented-programming.md)
- [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
