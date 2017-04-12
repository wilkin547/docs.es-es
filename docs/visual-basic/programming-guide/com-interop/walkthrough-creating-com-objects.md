---
title: 'Tutorial: Crear objetos COM con Visual Basic | Documentos de Microsoft'
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
- COM interop, creating COM objects
- COM objects, creating
- COM interop, walkthroughs
- object creation, COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: cce28e2be5914880107334bf2c4dc4dc645b4793
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a>Tutorial: Crear objetos COM con Visual Basic
Al crear nuevas aplicaciones o componentes, es mejor crear ensamblados de .NET Framework. Sin embargo, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] también facilita la exposición de un componente de .NET Framework a COM. Esto le permite proporcionar nuevos componentes para conjuntos de aplicaciones anteriores que requieren componentes COM. Este tutorial muestra cómo usar [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] exponer [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] objetos como objetos COM, con y sin la plantilla de clase COM.  
  
 Es la manera más fácil de exponer objetos COM mediante la plantilla de clase COM. La plantilla de clase COM crea una nueva clase y, a continuación, configura el proyecto para generar el nivel de clase e interoperabilidad como un objeto COM y registrarlo con el sistema operativo.  
  
> [!NOTE]
>  También puede exponer una clase creada en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] como un objeto COM para código no administrado, no es un verdadero objeto COM y no se puede usar por [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Para obtener más información, consulte [interoperabilidad COM en aplicaciones de .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a>Para crear un objeto COM mediante la plantilla de clase COM  
  
1.  Abra un nuevo proyecto de aplicación para Windows desde el **archivo** menú haciendo clic en **nuevo proyecto**.  
  
2.  En el **nuevo proyecto** cuadro de diálogo en el **tipos de proyecto** campo, compruebe que Windows está seleccionada. Seleccione **biblioteca de clases de** desde el **plantillas** y, a continuación, haga clic en **Aceptar**. Se muestra el nuevo proyecto.  
  
3.  Seleccione **Agregar nuevo elemento** desde el **proyecto** menú. El **Agregar nuevo elemento** se muestra el cuadro de diálogo.  
  
4.  Seleccione **clase COM** desde el **plantillas** y, a continuación, haga clic en **agregar**. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Agrega una nueva clase y configura el nuevo proyecto para la interoperabilidad COM.  
  
5.  Agregar código como propiedades, métodos y eventos a la clase COM.  
  
6.  Seleccione **generar ClassLibrary1** desde el **crear** menú. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]genera el ensamblado y registra el objeto COM con el sistema operativo.  
  
## <a name="creating-com-objects-without-the-com-class-template"></a>Crear objetos COM sin la plantilla de clase COM  
 También puede crear una clase COM manualmente en lugar de usar la plantilla de clase COM. Este procedimiento es útil cuando se trabaja desde la línea de comandos o cuando se desea más control sobre cómo se definen los objetos COM.  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a>Para configurar el proyecto para generar un objeto COM  
  
1.  Abra un nuevo proyecto de aplicación para Windows desde el **archivo** menú haciendo clic en **NewProject**.  
  
2.  En el **nuevo proyecto** cuadro de diálogo en el **tipos de proyecto** campo, compruebe que Windows está seleccionada. Seleccione **biblioteca de clases de** desde el **plantillas** y, a continuación, haga clic en **Aceptar**. Se muestra el nuevo proyecto.  
  
3.  En **el Explorador de soluciones**, haga clic en el proyecto y, a continuación, haga clic en **propiedades**. El **Project Designer** se muestra.  
  
4.  Haga clic en el **compilar** ficha.  
  
5.  Seleccione el **registrar para interoperabilidad COM** casilla de verificación.  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a>Para configurar el código de la clase para crear un objeto COM.  
  
1.  En **el Explorador de soluciones**, haga doble clic en **Class1.vb** para mostrar su código.  
  
2.  Cambie el nombre de la clase a `ComClass1`.  
  
3.  Agregue las siguientes constantes a `ComClass1`. Las constantes de identificador único global (GUID) que son necesarios para que los objetos COM va a almacenar.  
  
     [!code-vb[VbVbalrInterop&#2;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]  
  
4.  En el **herramientas** menú, haga clic en **crear Guid**. En el **crear GUID** cuadro de diálogo, haga clic en **formato del registro** y, a continuación, haga clic en **copia**. Haga clic en **Exit**.  
  
5.  Reemplace la cadena vacía para el `ClassId` con el GUID, llaves quitar espacio inicial y final. Por ejemplo, si el GUID proporcionado por Guidgen es `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` , a continuación, el código debe aparecer como sigue.  
  
     [!code-vb[VbVbalrInterop&3;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]  
  
6.  Repita los pasos anteriores para el `InterfaceId` y `EventsId` constantes, como en el ejemplo siguiente.  
  
     [!code-vb[VbVbalrInterop Nº&4;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]  
  
    > [!NOTE]
    >  Asegúrese de que los GUID son nuevos y únicos; de lo contrario, el componente COM podría entrar en conflicto con otros componentes COM.  
  
7.  Agregue el `ComClass` atributo `ComClass1`, especificando los GUID para el Id. de clase, el identificador de interfaz y el identificador de eventos, como en el ejemplo siguiente:  
  
     [!code-vb[VbVbalrInterop&#5;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]  
  
8.  Clases COM deben tener un sin parámetros `Public Sub New()` clase o constructor no se registrará correctamente. Agregue un constructor sin parámetros a la clase:  
  
     [!code-vb[VbVbalrInterop Nº&6;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]  
  
9. Agregue propiedades, métodos y eventos a la clase, finalizando con un `End Class` instrucción. Seleccione **generar solución** desde el **crear** menú. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]genera el ensamblado y registra el objeto COM con el sistema operativo.  
  
    > [!NOTE]
    >  Los objetos COM que genere con [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] no se pueden usar otros [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] aplicaciones porque no se encuentran los objetos COM es true. Si intenta agregar referencias a estos objetos COM producirá un error. Para obtener más información, consulte [interoperabilidad COM en aplicaciones de .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.ComClassAttribute></xref:Microsoft.VisualBasic.ComClassAttribute>   
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tutorial: Implementar la herencia mediante objetos COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [#Region (directiva)](../../../visual-basic/language-reference/directives/region-directive.md)   
 [Interoperabilidad COM en aplicaciones de .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)   
 [Solución de problemas de interoperabilidad](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
