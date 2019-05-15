---
title: 'Tutorial: Crear objetos COM con Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: 465f1d8141f51de179dbb4e963a8fcac8c09fa33
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592697"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a>Tutorial: Crear objetos COM con Visual Basic
Al crear nuevas aplicaciones o componentes, es mejor crear ensamblados de .NET Framework. Sin embargo, Visual Basic también resulta más fácil exponer un componente de .NET Framework a COM. Esto le permite proporcionar nuevos componentes para conjuntos de aplicaciones anteriores que requieren componentes COM. Este tutorial muestra cómo usar Visual Basic para exponer los objetos de .NET Framework como objetos COM, con y sin la plantilla de clase COM.  
  
 Es la manera más fácil exponer objetos COM mediante la plantilla de clase COM. La plantilla de clase COM crea una nueva clase y, a continuación, configura el proyecto para generar el nivel de clase e interoperabilidad como un objeto COM y registrarlo con el sistema operativo.  
  
> [!NOTE]
>  También puede exponer una clase creada en Visual Basic como un objeto COM para código no administrado, no es un verdadero objeto COM y no se puede usar Visual Basic. Para obtener más información, consulte [interoperabilidad COM en aplicaciones de .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a>Para crear un objeto COM mediante la plantilla de clase com.  
  
1. Abra un nuevo proyecto de aplicación de Windows desde el **archivo** menú haciendo **nuevo proyecto**.  
  
2. En el **nuevo proyecto** cuadro de diálogo en el **tipos de proyecto** campo, compruebe que Windows está seleccionada. Seleccione **biblioteca de clases** desde el **plantillas** lista y, a continuación, haga clic en **Aceptar**. Se muestra el nuevo proyecto.  
  
3. Seleccione **Agregar nuevo elemento** desde el **proyecto** menú. Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.  
  
4. Seleccione **clase COM** desde el **plantillas** lista y, a continuación, haga clic en **agregar**. Visual Basic agrega una nueva clase y configura el nuevo proyecto para la interoperabilidad COM.  
  
5. Agregue código como propiedades, métodos y eventos a la clase COM.  
  
6. Seleccione **generar ClassLibrary1** desde el **compilar** menú. Visual Basic compila el ensamblado y registra el objeto COM con el sistema operativo.  
  
## <a name="creating-com-objects-without-the-com-class-template"></a>Creación de objetos COM sin la plantilla de clase com.  
 También puede crear una clase COM manualmente en lugar de usar la plantilla de clase COM. Este procedimiento es útil cuando se trabaja desde la línea de comandos o cuando se desea tener más control sobre cómo se definen los objetos COM.  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a>Para configurar el proyecto para generar un objeto COM  
  
1. Abra un nuevo proyecto de aplicación de Windows desde el **archivo** menú haciendo **NewProject**.  
  
2. En el **nuevo proyecto** cuadro de diálogo en el **tipos de proyecto** campo, compruebe que Windows está seleccionada. Seleccione **biblioteca de clases** desde el **plantillas** lista y, a continuación, haga clic en **Aceptar**. Se muestra el nuevo proyecto.  
  
3. En el **Explorador de soluciones**, haga clic con el botón derecho del mouse en su proyecto y después seleccione **Propiedades**. El **Diseñador de proyectos** se muestra.  
  
4. Haga clic en la pestaña **Compilar**.  
  
5. Seleccione el **registrar para interoperabilidad COM** casilla de verificación.  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a>Para configurar el código de la clase para crear un objeto COM.  
  
1. En **el Explorador de soluciones**, haga doble clic en **Class1.vb** para mostrar su código.  
  
2. Cambie el nombre de la clase a `ComClass1`.  
  
3. Agregue las siguientes constantes a `ComClass1`. Almacenará las constantes de identificador único global (GUID) que los objetos COM se deben tener.  
  
     [!code-vb[VbVbalrInterop#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#2)]  
  
4. En el menú **Herramientas**, haga clic en **Crear GUID**. En el cuadro de diálogo **Crear GUID**, haga clic en **Formato de Registro** y luego en **Copiar**. Haga clic en **Salir**.  
  
5. Reemplace la cadena vacía para el `ClassId` con el GUID, llaves quitando el interlineado iniciales y finales. Por ejemplo, si el GUID proporcionado por Guidgen es `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` , a continuación, el código debería aparecer como sigue.  
  
     [!code-vb[VbVbalrInterop#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#3)]  
  
6. Repita los pasos anteriores para el `InterfaceId` y `EventsId` constantes, como en el ejemplo siguiente.  
  
     [!code-vb[VbVbalrInterop#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#4)]  
  
    > [!NOTE]
    >  Asegúrese de que los GUID son nuevos y únicos; en caso contrario, el componente COM podría entrar en conflicto con otros componentes COM.  
  
7. Agregar el `ComClass` atributo `ComClass1`, especificando el GUID para el Id. de clase, el Id. de interfaz y el identificador de eventos en el ejemplo siguiente:  
  
     [!code-vb[VbVbalrInterop#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#5)]  
  
8. Clases COM deben tener una sin parámetros `Public Sub New()` constructor o la clase no se registrará correctamente. Agregue un constructor sin parámetros a la clase:  
  
     [!code-vb[VbVbalrInterop#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#6)]  
  
9. Agregue propiedades, métodos y eventos a la clase, finalizando con un `End Class` instrucción. Seleccione **compilar solución** desde el **compilar** menú. Visual Basic compila el ensamblado y registra el objeto COM con el sistema operativo.  
  
    > [!NOTE]
    >  Los objetos COM que genere con Visual Basic no pueden usarse por otras aplicaciones de Visual Basic, porque no son objetos COM es true. Intenta agregar referencias a estos objetos COM, producirá un error. Para obtener más información, consulte [interoperabilidad COM en aplicaciones de .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ComClassAttribute>
- [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)
- [Tutorial: Implementar la herencia mediante objetos COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [#Region (directiva)](../../../visual-basic/language-reference/directives/region-directive.md)
- [Interoperabilidad COM en aplicaciones .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [Solución de problemas de interoperabilidad](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
