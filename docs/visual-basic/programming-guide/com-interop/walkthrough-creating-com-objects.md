---
title: "Tutorial: Crear objetos COM con Visual Basic | Microsoft Docs"
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
  - "interoperabilidad COM, crear objetos COM"
  - "interoperabilidad COM, tutoriales"
  - "objetos COM, crear"
  - "objetos COM, tutoriales"
  - "creación de objetos, objetos COM"
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: 30
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 30
---
# Tutorial: Crear objetos COM con Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Cuando se crean nuevas aplicaciones o componentes, es mejor crear ensamblados de .NET Framework.  No obstante, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] facilita también la exposición de un componente de .NET Framework en COM.  De esta manera, puede proporcionar nuevos componentes para conjuntos de aplicaciones anteriores que requieren componentes COM.  En este tutorial se muestra cómo utilizar [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] para exponer los objetos de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] como objetos COM, tanto con la plantilla de clase COM como sin ella.  
  
 El modo más sencillo de exponer un objeto COM es utilizar la plantilla de clase COM.  Esta plantilla crea una clase nueva y, a continuación, configura el proyecto para generar la clase y el nivel de interoperabilidad como un objeto COM y registra este objeto en el sistema operativo.  
  
> [!NOTE]
>  También puede exponer una clase creada en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] como un objeto COM para su uso en código no administrado; sin embargo, no se trata de un objeto COM auténtico y [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] no lo puede usar.  Para obtener más información, vea [Interoperabilidad COM en aplicaciones .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Para crear un objeto COM mediante la plantilla de clase COM  
  
1.  Abra un nuevo proyecto de aplicación para Windows en el menú **Archivo**; para ello, haga clic en **Nuevo proyecto**.  
  
2.  En el cuadro de diálogo **Nuevo proyecto**, situado bajo el campo **Tipos de proyecto**, compruebe que se ha seleccionado Windows.  Seleccione **Biblioteca de clases** en la lista **Plantillas** y, a continuación, haga clic en **Aceptar**.  Aparecerá el proyecto nuevo.  
  
3.  Seleccione **Agregar nuevo elemento** en el menú **Proyecto**.  Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.  
  
4.  Seleccione **Clase COM** en la lista **Plantillas** y, a continuación, haga clic en **Agregar**.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] agrega una nueva clase y configura el nuevo proyecto para la interoperabilidad COM.  
  
5.  Agregue código a la clase COM, como propiedades, métodos y eventos.  
  
6.  Seleccione **Compilar ClassLibrary1** en el menú **Compilar**.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] compila el ensamblado y registra el objeto COM con el sistema operativo.  
  
## Crear objetos COM sin la plantilla de clase COM  
 También puede crear una clase COM manualmente en lugar de utilizar la plantilla de clase COM.  Este procedimiento resulta útil cuando se trabaja desde la línea de comandos o cuando se desea lograr más control sobre la definición de los objetos COM.  
  
#### Para configurar el proyecto para generar un objeto COM  
  
1.  Abra un nuevo proyecto de aplicación para Windows desde el menú **Archivo**; para ello, haga clic en **Nuevo proyecto**.  
  
2.  En el cuadro de diálogo **Nuevo proyecto**, situado bajo el campo **Tipos de proyecto**, compruebe que se ha seleccionado Windows.  Seleccione **Biblioteca de clases** en la lista **Plantillas** y, a continuación, haga clic en **Aceptar**.  Aparecerá el proyecto nuevo.  
  
3.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en su proyecto y, a continuación, seleccione **Propiedades**.  Se mostrará el **Diseñador de proyectos**.  
  
4.  Haga clic en la ficha **Compilar**.  
  
5.  Active la casilla **Registrar para interoperabilidad COM**.  
  
#### Para configurar el código de la clase para crear un objeto COM  
  
1.  En el **Explorador de soluciones**, haga doble clic en **Class1.vb** para mostrar el código que contiene.  
  
2.  Cambie el nombre de la clase a `ComClass1`.  
  
3.  Agregue a `ComClass1` las constantes que se especifican a continuación.  Estas constantes almacenarán las constantes de identificador único global \(GUID\) que necesitan los objetos COM.  
  
     [!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#2)]  
  
4.  En el menú **Herramientas**, haga clic en **Crear GUID**.  En el cuadro de diálogo **Crear GUID**, haga clic en **Formato del Registro** y, a continuación, en **Copiar**.  Haga clic en **Salir**.  
  
5.  Reemplace la cadena vacía de `ClassId` con el GUID, y quite las llaves de apertura y cierre.  Por ejemplo, si el GUID proporcionado por Guidgen es `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"`, el código debería aparecer como se muestra a continuación.  
  
     [!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#3)]  
  
6.  Repita los pasos anteriores para las constantes `InterfaceId` y `EventsId`, como en el ejemplo siguiente.  
  
     [!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#4)]  
  
    > [!NOTE]
    >  Asegúrese de que los GUID son nuevos y únicos; de lo contrario, el componente COM podría entrar en conflicto con otros componentes COM.  
  
7.  Agregue el atributo `ComClass` a `ComClass1`, especificando los GUID correspondientes al Id. de clase, al Id. de interfaz y a los Id. de eventos, como en el siguiente ejemplo:  
  
     [!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#5)]  
  
8.  Las clases COM deben tener un constructor `Public Sub New()` sin parámetros; de lo contrario, la clase no se registrará correctamente.  Agregue un constructor sin parámetros a la clase:  
  
     [!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#6)]  
  
9. Agregue propiedades, métodos y eventos a la clase, y agregue la instrucción `End Class` al final.  En el menú **Compilar**, seleccione **Compilar solución** .  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] compila el ensamblado y registra el objeto COM con el sistema operativo.  
  
    > [!NOTE]
    >  Los objetos COM que genere con [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] no se pueden utilizar en otras aplicaciones de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] porque no son auténticos objetos COM.  Si intenta agregar referencias a estos objetos COM se producirá un error.  Para obtener información detallada, vea [Interoperabilidad COM en aplicaciones .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.ComClassAttribute>   
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tutorial: Implementar la herencia mediante objetos COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [\#Region \(Directiva\)](../../../visual-basic/language-reference/directives/region-directive.md)   
 [Interoperabilidad COM en aplicaciones .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)   
 [Solución de problemas de interoperabilidad](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)