---
title: 'Tutorial: Mostrar los datos enlazados en un control DataRepeater (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
ms.openlocfilehash: 8e64a819e9670a29e97140a32c81f5ff9006f83e
ms.sourcegitcommit: 2ad7d06f4f469b5d8a5280ac0e0289a81867fc8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "35231520"
---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a>Tutorial: Mostrar los datos enlazados en un control DataRepeater (Visual Studio)
En este tutorial se proporciona un escenario básico de principio a fin para mostrar datos enlazados en un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
## <a name="prerequisite"></a>Requisito previo  
 Este tutorial requiere la base de datos de ejemplo Northwind.  
  
 Si no tiene esta base de datos en el equipo de desarrollo, puede descargarlo desde Microsoft Download Center. Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
## <a name="overview"></a>Información general  
 La primera parte de este tutorial se compone de cuatro tareas principales:  
  
-   Crear una solución.  
  
-   Agregar un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
-   Agregar un origen de datos.  
  
-   Agregar controles enlazados a datos.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-a-datarepeater-solution"></a>Crear una solución DataRepeater  
 En el primer paso, creará un proyecto y una solución.  
  
#### <a name="to-create-a-datarepeater-solution"></a>Para crear una solución DataRepeater  
  
1.  En el menú **Archivo** de Visual Studio, haga clic en **Nuevo proyecto**.  
  
2.  En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto** , expanda **Visual Basic**y, a continuación, haga clic en **Windows**.  
  
3.  En el panel **Plantillas** , haga clic en **Aplicación de Windows Forms**.  
  
4.  En el cuadro **Nombre** , escriba `DataRepeaterApp`.  
  
5.  Haga clic en **Aceptar**.  
  
     Se abre el Diseñador de Windows Forms.  
  
6.  Seleccione el formulario en el Diseñador de Windows Forms. En la ventana **Propiedades** , establezca la propiedad **Size** en `800, 700`.  
  
## <a name="adding-a-datarepeater-control"></a>Agregar un control DataRepeater  
 En este paso, agregará un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> al formulario.  
  
#### <a name="to-add-a-datarepeater-control"></a>Para agregar un control DataRepeater  
  
1.  En el menú **Ver** , haga clic en **Cuadro de herramientas**.  
  
     Se abrirá el **Cuadro de herramientas** .  
  
2.  Seleccionar la pestaña **Visual Basic PowerPacks** .  
  
3.  Arrastre un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> a **Form1**.  
  
4.  En la ventana Propiedades, establezca la propiedad **Location** en `0, 25`.  
  
5.  Establezca la propiedad **Size** en `460, 600`.  
  
## <a name="adding-a-data-source"></a>Agregar un origen de datos  
 En este paso, agregará un origen de datos para el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
#### <a name="to-add-a-data-source"></a>Para agregar un origen de datos  
  
1.  En el menú **Datos** , haga clic en **Mostrar orígenes de datos**.  
  
2.  En la ventana **Orígenes de datos** , seleccione **Agregar nuevo origen de datos**.  
  
3.  Seleccione **Base de datos** en la página **Elegir un tipo de datos de origen** y luego haga clic en **Siguiente**.  
  
4.  En la página **Elegir la conexión de datos** , siga uno de estos procedimientos:  
  
    -   Si existe alguna conexión de datos a la base de datos de ejemplo Northwind disponible en el cuadro de lista desplegable, haga clic en ella.  
  
         O bien  
  
    -   Haga clic en **Nueva conexión** para configurar una nueva conexión de datos. Para obtener más información, consulte [agregar nuevas conexiones](/visualstudio/data-tools/add-new-connections).  
  
5.  Si la base de datos requiere una contraseña, seleccione la opción para incluir datos confidenciales y, a continuación, haga clic en **Siguiente**.  
  
    > [!NOTE]
    >  Si aparece un cuadro de diálogo, haga clic en **Sí** para guardar el archivo en su proyecto.  
  
6.  Haga clic en **Siguiente** en la página **Guardar la cadena de conexión en el archivo de configuración de la aplicación** .  
  
7.  Expanda el nodo **Tablas** en la página **Elija los objetos de base de datos** .  
  
8.  Seleccione las casillas situadas junto a las tablas **Customers** y **Orders** y después haga clic en **Finalizar**.  
  
     **NorthwindDataSet** se agrega al proyecto y las tablas **Customers** y **Orders** aparecen en la ventana **Orígenes de datos** .  
  
## <a name="adding-data-bound-controls"></a>Agregar controles enlazados a datos  
 En este paso, agregará controles enlazados a datos a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
#### <a name="to-add-data-bound-controls"></a>Para agregar controles enlazados a datos  
  
1.  En la ventana **Orígenes de datos** , seleccione el nodo de nivel superior para la tabla **Customers** .  
  
2.  Cambie el tipo de colocación de la tabla a **Detalles** haciendo clic en **Detalles** en la lista desplegable del nodo de la tabla.  
  
3.  Seleccione el nodo de la tabla **Customers** y arrástrelo a la región de la plantilla de elemento (la región superior) del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
     Se agrega un control <xref:System.Windows.Forms.BindingNavigator> al formulario y se agregan los componentes **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**y **CustomersBindingNavigator** a la bandeja de componentes.  
  
4.  Seleccione todos los campos y sus etiquetas asociadas y colóquelos cerca del borde izquierdo de la región de la plantilla de elemento.  
  
5.  Seleccione los cinco últimos campos (**Región**, **Código postal**, **País**, **Teléfono**y **Fax**) y sus etiquetas asociadas y muévalos arriba y a la derecha de los seis primeros campos.  
  
6.  Seleccione la plantilla de elemento (la región superior del control).  
  
7.  En la ventana Propiedades, establezca la propiedad **Size** en `427, 170`.  
  
 En este punto, tendrá una aplicación operativa que mostrará una lista repetitiva de clientes. Puede presionar F5 para ejecutar la aplicación, cambiar los datos y agregar o eliminar registros de cliente.  
  
 En los siguientes pasos opcionales, obtendrá información sobre cómo personalizar el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
## <a name="next-steps-optional"></a>Pasos siguientes (opcionales)  
 Esta parte del tutorial consta de cuatro tareas opcionales:  
  
-   Cambiar la apariencia del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
-   Impedir que los usuarios agreguen o eliminen registros.  
  
-   Agregar capacidad de búsqueda al control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
-   Agregar una tabla maestra y de detalles al control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a>Cambiar la apariencia del control DataRepeater  
 En este paso opcional, cambiará el valor `BackColor` del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> en tiempo de diseño. También agregará código para mostrar las filas en colores alternos y cambiar el valor `ForeColor` de una etiqueta de manera condicional.  
  
#### <a name="to-change-the-appearance-of-the-control"></a>Para cambiar la apariencia del control  
  
1.  En el Diseñador de Windows Forms, seleccione la región principal (inferior) del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
2.  En la ventana Propiedades, establezca la propiedad `BackColor` en blanco.  
  
3.  Haga doble clic en <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> para abrir el Editor de código.  
  
4.  En el Editor de código, en la lista desplegable de eventos, haga clic en **DrawItem**.  
  
5.  En el controlador de eventos de <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> , agregue el código siguiente para alternar el valor `BackColor`.  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]  
  
6.  En el controlador de eventos de <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> , agregue el código siguiente para cambiar el valor `ForeColor` de una etiqueta según una condición:  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]  
  
7.  Presione F5 para ejecutar la aplicación y ver las personalizaciones.  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a>Impedir que los usuarios agreguen o eliminen registros  
 En este paso opcional, agregará código que impida que los usuarios agreguen o eliminen registros en el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a>Para impedir que los usuarios agreguen y eliminen registros  
  
1.  En el Diseñador de Windows Forms, haga doble clic en el formulario para abrir el Editor de código.  
  
2.  Agregue el código siguiente al evento `Form_Load` :  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]  
  
3.  En la lista desplegable Nombre de clase, haga clic en **BindingNavigatorDeleteItem**. En la lista desplegable Nombre de método, haga clic en **EnabledChanged**.  
  
4.  Agregue el código siguiente al controlador de eventos `BindingNavigatorDeleteItem_EnabledChanged` :  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]  
  
    > [!NOTE]
    >  Este paso es necesario porque <xref:System.Windows.Forms.BindingSource> habilitará el botón **DeleteItem** cada vez que cambie el registro actual.  
  
5.  Presione F5 para ejecutar la aplicación. Observe que el botón **DeleteItem** está deshabilitado y que no se pueden eliminar elementos presionando la tecla Supr.  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a>Agregar capacidad de búsqueda al control DataRepeater  
 En este paso opcional, implementará la capacidad de búsqueda de un valor en el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> . Si se encuentra la cadena de búsqueda, el control selecciona el elemento que contiene el valor y desplaza el elemento en la vista.  
  
#### <a name="to-add-search-capability"></a>Para agregar capacidad de búsqueda  
  
1.  Arrastre un control <xref:System.Windows.Forms.TextBox> desde el **Cuadro de herramientas** hasta el formulario que contenga el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
     Colóquelo bajo el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
2.  En la ventana Propiedades, cambie la propiedad **Name** a **SearchTextBox**.  
  
3.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** hasta el formulario que contenga el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> . Colóquelo bajo el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
4.  En la ventana Propiedades, cambie la propiedad **Name** a **SearchButton**. Cambie la propiedad **Text** a **Search**.  
  
5.  Haga doble clic en el control <xref:System.Windows.Forms.Button> para abrir el Editor de código y agregue el código siguiente al controlador de eventos `SearchButton_Click` .  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]  
  
6.  Presione F5 para ejecutar la aplicación. Escriba un identificador de cliente en **SearchTextBox** y haga clic en el botón **Buscar** .  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a>Agregar una tabla maestra y de detalles a DataRepeater  
 En este paso opcional, agregará un segundo control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> para mostrar los pedidos relacionados para cada cliente.  
  
#### <a name="to-add-a-master-and-detail-table"></a>Para agregar una tabla maestra y de detalles  
  
1.  Arrastre un segundo control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> de la pestaña **Visual Basic PowerPacks** del **Cuadro de herramientas** al formulario.  
  
2.  En la ventana Propiedades, establezca la propiedad **Location** en `465, 25`.  
  
3.  Establezca la propiedad **Size** en `315, 600`.  
  
4.  En la ventana **Orígenes de datos** , expanda el nodo de la tabla **Customers** y seleccione el nodo de detalle de la tabla **Orders** .  
  
5.  Cambie el tipo de colocación de esta tabla **Orders** a Detalles haciendo clic en **Detalles** en la lista desplegable del nodo de la tabla.  
  
6.  Arrastre este nodo de la tabla **Orders** a la región de la plantilla de elemento (la región superior) del segundo control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
     Se agregan un componente **OrdersBindingSource** y un componente **OrdersTableAdapter** a la bandeja de componentes.  
  
7.  Presione F5 para ejecutar la aplicación. Al seleccionar cada cliente en el primer control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> , los pedidos de ese cliente se muestran en el segundo control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
## <a name="see-also"></a>Vea también  
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Mostrar los datos enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Mostrar controles no enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [Cambiar el diseño de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [Mostrar los encabezados de los elementos en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)  
 [Buscar datos en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)  
 [Cómo: crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [Cambiar la apariencia de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Deshabilitar las operaciones de agregar y eliminar elementos DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)  
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
