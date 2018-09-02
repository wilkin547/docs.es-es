---
title: 'Tutorial: Serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
ms.openlocfilehash: 54859b3065e8e9bb9680d8b6bf7946b393f73b9f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402591"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a>Tutorial: Serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute
A veces, los controles personalizados expondrá una colección como una propiedad. Este tutorial muestra cómo usar el <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> clase para controlar cómo se serializa una colección en tiempo de diseño. Aplicar el <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> valor a la propiedad de colección se asegura de que se va a serializar la propiedad.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute](https://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Permisos suficientes para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde está instalado Visual Studio.  
  
## <a name="creating-a-control-that-has-a-serializable-collection"></a>Crear un Control que tiene una colección Serializable  
 El primer paso es crear un control que tiene una colección serializable como una propiedad. Puede editar el contenido de esta colección con el **Editor de la colección**, que se puede acceder desde el **propiedades** ventana.  
  
#### <a name="to-create-a-control-with-a-serializable-collection"></a>Para crear un control con una colección serializable  
  
1.  Cree un proyecto de biblioteca de controles de Windows denominado `SerializationDemoControlLib`. Para obtener más información, consulte [plantilla Biblioteca de controles de Windows](https://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  Cambiar el nombre de `UserControl1` a `SerializationDemoControl`. Para obtener más información, consulte [Cómo: cambiar el nombre de los identificadores](https://msdn.microsoft.com/library/2430f732-2b70-4516-8cf6-a7bb71cc9724).  
  
3.  En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> propiedad `10`.  
  
4.  Colocar un <xref:System.Windows.Forms.TextBox> en controlar la `SerializationDemoControl`.  
  
5.  Seleccione el control <xref:System.Windows.Forms.TextBox>. En el **propiedades** ventana, establezca las propiedades siguientes.  
  
    |Property|Cambiar a|  
    |--------------|---------------|  
    |**Multiline**|`true`|  
    |**Acoplar**|<xref:System.Windows.Forms.DockStyle.Fill>|  
    |**Barras de desplazamiento**|<xref:System.Windows.Forms.ScrollBars.Vertical>|  
    |**ReadOnly**|`true`|  
  
6.  En el **Editor de código**, declare un campo de matriz de cadena denominado `stringsValue` en `SerializationDemoControl`.  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7.  Definir la `Strings` propiedad en el `SerializationDemoControl`.  
  
> [!NOTE]
>  El <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> valor se utiliza para habilitar la serialización de la colección.  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1.  Presione F5 para compilar el proyecto y ejecutar el control en **UserControl Test Container**.  
  
2.  Buscar el `Strings` propiedad en el <xref:System.Windows.Forms.PropertyGrid> de la **UserControl Test Container**. Haga clic en el `Strings` propiedad, a continuación, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) para abrir el **deEditordecoleccióndecadenas**.  
  
3.  Escriba varias cadenas en el **Editor de colección de cadenas**. Deberá separarlos presionando la tecla ENTRAR al final de cada cadena. Haga clic en **Aceptar** cuando haya terminado de escribir cadenas.  
  
> [!NOTE]
>  Aparecen las cadenas que escribió en el <xref:System.Windows.Forms.TextBox> de la `SerializationDemoControl`.  
  
## <a name="serializing-a-collection-property"></a>Serializar una propiedad de colección  
 Para probar el comportamiento de serialización del control, que lo coloca en un formulario y cambiar el contenido de la colección con el **Editor de la colección**. Puede ver el estado de la colección serializada si examina un archivo de diseñador especial, en la que el **Diseñador de Windows Forms** emite el código.  
  
#### <a name="to-serialize-a-collection"></a>Para serializar una colección  
  
1.  Agregar un proyecto de aplicación de Windows a la solución. Dé un nombre al proyecto `SerializationDemoControlTest`.  
  
2.  En el **cuadro de herramientas**, busque la pestaña denominada **componentes SerializationDemoControlLib**. En esta pestaña, puede encontrar el `SerializationDemoControl`. Para más información, consulte [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
3.  Colocar un `SerializationDemoControl` en el formulario.  
  
4.  Buscar el `Strings` propiedad en el **propiedades** ventana. Haga clic en el `Strings` propiedad, a continuación, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) para abrir el **deEditordecoleccióndecadenas**.  
  
5.  Escriba varias cadenas en el **Editor de colección de cadenas**. Deberá separarlos presionando la tecla ENTRAR al final de cada cadena. Haga clic en **Aceptar** cuando haya terminado de escribir cadenas.  
  
> [!NOTE]
>  Aparecen las cadenas que escribió en el <xref:System.Windows.Forms.TextBox> de la `SerializationDemoControl`.  
  
1.  En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.  
  
2.  Abra el **Form1** nodo. Debajo es un archivo denominado **Form1.Designer.cs** o **Form1.Designer.vb**. Este es el archivo en el que el **Diseñador de Windows Forms** emite código que representa el estado de tiempo de diseño del formulario y sus controles secundarios. Abra este archivo en el **Editor de código**.  
  
3.  Abra la región denominada **código generado por el Diseñador de formularios de Windows** y busque la sección con la etiqueta **serializationDemoControl1**. Por debajo de esta etiqueta es el código que representa el estado serializado del control. Las cadenas que escribió en el paso 5 aparecerán en una asignación a la `Strings` propiedad. Los siguientes ejemplos de código en C# y Visual Basic, se muestra código similar a lo que verá si ha escrito las cadenas "rojo", "orange" y "amarillo".  
  
    ```csharp  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
    
    ```vb  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```
  
4.  En el **Editor de código**, cambie el valor de la <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> en el `Strings` propiedad <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.  
  
    ```csharp  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
    ```vb  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
5. Vuelva a generar la solución y repita los pasos 3 y 4.  
  
> [!NOTE]
>  En este caso, el **Diseñador de Windows Forms** no emite ninguna asignación a la `Strings` propiedad.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Una vez que sepa cómo serializar una colección de tipos estándares, considere la posibilidad de integrar los controles personalizados más profundamente en el entorno de tiempo de diseño. Los temas siguientes describen cómo mejorar la integración de tiempo de diseño de los controles personalizados:  
  
-   [Arquitectura en tiempo de diseño](https://msdn.microsoft.com/library/4881917b-628f-4689-b872-472e4f8a4e3a)  
  
-   [Atributos en controles de Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
  
-   [Información general de la serialización de diseñador](https://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
  
-   [Tutorial: Crear un control de Windows Forms que aproveche las características en tiempo de diseño de Visual Studio](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>  
 [Información general de la serialización de diseñador](https://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
 [Cómo: serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute](https://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)  
 [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
