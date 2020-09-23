---
title: 'Tutorial: Creación de objetos COM'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: 90a21b70b45902a9f4fd559a97e777f26043fffb
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075621"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a>Tutorial: Crear objetos COM con Visual Basic

Al crear nuevas aplicaciones o componentes, es mejor crear ensamblados de .NET Framework. Sin embargo, Visual Basic también facilita la exposición de un componente de .NET Framework a COM. Esto le permite proporcionar nuevos componentes para conjuntos de aplicaciones anteriores que requieren componentes COM. En este tutorial se muestra cómo usar Visual Basic para exponer objetos .NET Framework como objetos COM, con y sin la plantilla de clase COM.  
  
 La forma más fácil de exponer objetos COM es usar la plantilla de clase COM. Esta plantilla crea una nueva clase y, a continuación, configura el proyecto para generar la clase con una capa de interoperabilidad como un objeto COM y registrarla en el sistema operativo.  
  
> [!NOTE]
> Aunque también puede exponer una clase creada en Visual Basic como un objeto COM para el uso de código no administrado, no es un objeto COM verdadero y Visual Basic no puede usar. Para obtener más información, consulte [interoperabilidad com en aplicaciones .NET Framework](com-interoperability-in-net-framework-applications.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a>Para crear un objeto COM mediante la plantilla de clase COM  
  
1. Abra un nuevo proyecto de aplicación de Windows desde el menú **archivo** haciendo clic en **nuevo proyecto**.  
  
2. En el cuadro de diálogo **nuevo proyecto** , en el campo **tipos de proyecto** , compruebe que está seleccionada la opción Windows. Seleccione **biblioteca de clases** en la lista **plantillas** y, a continuación, haga clic en **Aceptar**. Se muestra el nuevo proyecto.  
  
3. Seleccione **Agregar nuevo elemento** en el menú **proyecto** . Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.  
  
4. Seleccione **clase com** en la lista de **plantillas** y, a continuación, haga clic en **Agregar**. Visual Basic agrega una nueva clase y configura el nuevo proyecto para la interoperabilidad COM.  
  
5. Agregue código como propiedades, métodos y eventos a la clase COM.  
  
6. Seleccione **compilar ClassLibrary1** en el menú **compilar** . Visual Basic crea el ensamblado y registra el objeto COM con el sistema operativo.  
  
## <a name="creating-com-objects-without-the-com-class-template"></a>Crear objetos COM sin la plantilla de clase COM  

 También puede crear una clase COM manualmente en lugar de usar la plantilla de clase COM. Este procedimiento es útil cuando se trabaja desde la línea de comandos o cuando se desea tener más control sobre cómo se definen los objetos COM.  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a>Para configurar el proyecto para generar un objeto COM  
  
1. Abra un nuevo proyecto de aplicación de Windows desde el menú **archivo** haciendo clic en **NewProject**.  
  
2. En el cuadro de diálogo **nuevo proyecto** , en el campo **tipos de proyecto** , compruebe que está seleccionada la opción Windows. Seleccione **biblioteca de clases** en la lista **plantillas** y, a continuación, haga clic en **Aceptar**. Se muestra el nuevo proyecto.  
  
3. En el **Explorador de soluciones**, haga clic con el botón derecho del mouse en su proyecto y después seleccione **Propiedades**. Se muestra el **Diseñador de proyectos** .  
  
4. Haga clic en la pestaña **Compilar**.  
  
5. Active la casilla **registrar para interoperabilidad com** .  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a>Para configurar el código de la clase para crear un objeto COM  
  
1. En **Explorador de soluciones**, haga doble clic en **Class1. VB** para mostrar su código.  
  
2. Cambie el nombre de la clase a `ComClass1`.  
  
3. Agregue las siguientes constantes a `ComClass1` . Almacenarán las constantes de identificador único global (GUID) que los objetos COM deben tener.  
  
     [!code-vb[VbVbalrInterop#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#2)]  
  
4. En el menú **Herramientas**, haga clic en **Crear GUID**. En el cuadro de diálogo **Crear GUID**, haga clic en **Formato de Registro** y luego en **Copiar**. Haga clic en **Salir**.  
  
5. Reemplace la cadena vacía del `ClassId` con el GUID y quite las llaves iniciales y finales. Por ejemplo, si el GUID proporcionado por Guidgen es `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` , el código debe aparecer de la siguiente manera.  
  
     [!code-vb[VbVbalrInterop#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#3)]  
  
6. Repita los pasos anteriores para las `InterfaceId` `EventsId` constantes y, como en el ejemplo siguiente.  
  
     [!code-vb[VbVbalrInterop#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#4)]  
  
    > [!NOTE]
    > Asegúrese de que los GUID son nuevos y únicos; de lo contrario, el componente COM podría estar en conflicto con otros componentes COM.  
  
7. Agregue el `ComClass` atributo a `ComClass1` , especificando los GUID para el identificador de clase, el identificador de interfaz y el identificador de eventos, como en el ejemplo siguiente:  
  
     [!code-vb[VbVbalrInterop#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#5)]  
  
8. Las clases COM deben tener un constructor sin parámetros `Public Sub New()` o la clase no se registrará correctamente. Agregue un constructor sin parámetros a la clase:  
  
     [!code-vb[VbVbalrInterop#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#6)]  
  
9. Agregue propiedades, métodos y eventos a la clase, y finalice con una `End Class` instrucción. Seleccione **compilar solución** en el menú **compilar** . Visual Basic crea el ensamblado y registra el objeto COM con el sistema operativo.  
  
    > [!NOTE]
    > Los objetos COM generados con Visual Basic no pueden ser utilizados por otras aplicaciones Visual Basic porque no son objetos COM verdaderos. Los intentos de agregar referencias a estos objetos COM producirán un error. Para obtener más información, consulte [interoperabilidad com en aplicaciones .NET Framework](com-interoperability-in-net-framework-applications.md).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ComClassAttribute>
- [Interoperabilidad COM](index.md)
- [Tutorial: Implementación de la herencia mediante objetos COM](walkthrough-implementing-inheritance-with-com-objects.md)
- [#Region (Directiva)](../../language-reference/directives/region-directive.md)
- [Interoperabilidad COM en aplicaciones .NET Framework](com-interoperability-in-net-framework-applications.md)
- [Solución de problemas de interoperabilidad](troubleshooting-interoperability.md)
