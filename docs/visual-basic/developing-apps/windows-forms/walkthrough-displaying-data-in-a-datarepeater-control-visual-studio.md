---
title: 'Tutorial: Mostrar datos en un Control DataRepeater (Visual Studio) | Documentos de Microsoft'
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 09f15c94c3d5a3387935c8d3f4758c0ecfd7cfcd
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a>Tutorial: Mostrar los datos enlazados en un control DataRepeater (Visual Studio)
Este tutorial proporciona un escenario básico de principio a fin para mostrar datos enlazados en un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="prerequisite"></a>Requisito previo  
 Este tutorial requiere la base de datos de ejemplo Northwind.  
  
 Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del [Centro de descarga de Microsoft](http://go.microsoft.com/fwlink/?LinkID=98088). Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](https://msdn.microsoft.com/library/bb399411).  
  
## <a name="overview"></a>Información general  
 La primera parte de este tutorial se compone de cuatro tareas principales:  
  
-   Crear una solución.  
  
-   Agregar un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
-   Agregar un origen de datos.  
  
-   Agregar controles enlazados a datos.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
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
 En este paso, agregará un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control al formulario.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
#### <a name="to-add-a-datarepeater-control"></a>Para agregar un control DataRepeater  
  
1.  En el menú **Ver** , haga clic en **Cuadro de herramientas**.  
  
     Se abrirá el **Cuadro de herramientas** .  
  
2.  Seleccionar la pestaña **Visual Basic PowerPacks** .  
  
3.  Arrastre un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control **Form1**.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
4.  En la ventana Propiedades, establezca la propiedad **Location** en `0, 25`.  
  
5.  Establezca la propiedad **Size** en `460, 600`.  
  
## <a name="adding-a-data-source"></a>Agregar un origen de datos  
 En este paso, agregará un origen de datos para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
#### <a name="to-add-a-data-source"></a>Para agregar un origen de datos  
  
1.  En el menú **Datos** , haga clic en **Mostrar orígenes de datos**.  
  
2.  En la ventana **Orígenes de datos** , seleccione **Agregar nuevo origen de datos**.  
  
3.  Seleccione **Base de datos** en la página **Elegir un tipo de datos de origen** y luego haga clic en **Siguiente**.  
  
4.  En la página **Elegir la conexión de datos** , siga uno de estos procedimientos:  
  
    -   Si existe alguna conexión de datos a la base de datos de ejemplo Northwind disponible en el cuadro de lista desplegable, haga clic en ella.  
  
         O bien  
  
    -   Haga clic en **Nueva conexión** para configurar una nueva conexión de datos. Para obtener más información, consulte [Cómo: crear conexiones a bases de datos de SQL Server](http://msdn.microsoft.com/en-us/360c340d-e5a6-4a7e-a569-e95d500be43d).  
  
5.  Si la base de datos requiere una contraseña, seleccione la opción para incluir datos confidenciales y, a continuación, haga clic en **Siguiente**.  
  
    > [!NOTE]
    >  Si aparece un cuadro de diálogo, haga clic en **Sí** para guardar el archivo en su proyecto.  
  
6.  Haga clic en **Siguiente** en la página **Guardar la cadena de conexión en el archivo de configuración de la aplicación** .  
  
7.  Expanda el nodo **Tablas** en la página **Elija los objetos de base de datos** .  
  
8.  Seleccione las casillas situadas junto a las tablas **Customers** y **Orders** y después haga clic en **Finalizar**.  
  
     **NorthwindDataSet** se agrega al proyecto y las tablas **Customers** y **Orders** aparecen en la ventana **Orígenes de datos** .  
  
## <a name="adding-data-bound-controls"></a>Agregar controles enlazados a datos  
 En este paso, agregará controles enlazados a datos a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
#### <a name="to-add-data-bound-controls"></a>Para agregar controles enlazados a datos  
  
1.  En la ventana **Orígenes de datos** , seleccione el nodo de nivel superior para la tabla **Customers** .  
  
2.  Cambie el tipo de colocación de la tabla a **Detalles** haciendo clic en **Detalles** en la lista desplegable del nodo de la tabla.  
  
3.  Seleccione el **clientes** nodo de tabla y arrástrelo a la región de plantilla de elementos (la región superior) de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
     Un <xref:System.Windows.Forms.BindingNavigator>se agrega el control al formulario y el **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**, y **CustomersBindingNavigator** componentes se agregan a la Bandeja de componentes.</xref:System.Windows.Forms.BindingNavigator>  
  
4.  Seleccione todos los campos y sus etiquetas asociadas y colóquelos cerca del borde izquierdo de la región de la plantilla de elemento.  
  
5.  Seleccione los cinco últimos campos (**Región**, **Código postal**, **País**, **Teléfono**y **Fax**) y sus etiquetas asociadas y muévalos arriba y a la derecha de los seis primeros campos.  
  
6.  Seleccione la plantilla de elemento (la región superior del control).  
  
7.  En la ventana Propiedades, establezca la propiedad **Size** en `427, 170`.  
  
 En este punto, tendrá una aplicación operativa que mostrará una lista repetitiva de clientes. Puede presionar F5 para ejecutar la aplicación, cambiar los datos y agregar o eliminar registros de cliente.  
  
 En los siguientes pasos opcionales, obtendrá información sobre cómo personalizar el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="next-steps-optional"></a>Pasos siguientes (opcionales)  
 Esta parte del tutorial consta de cuatro tareas opcionales:  
  
-   Cambiar la apariencia de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
-   Impedir que los usuarios agreguen o eliminen registros.  
  
-   Agregar capacidad de búsqueda para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
-   Agregar una tabla de maestro y detalles para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a>Cambiar la apariencia del control DataRepeater  
 En este paso opcional, cambia el `BackColor` de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control en tiempo de diseño.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> También agregará código para mostrar las filas en colores alternos y cambiar el valor `ForeColor` de una etiqueta de manera condicional.  
  
#### <a name="to-change-the-appearance-of-the-control"></a>Para cambiar la apariencia del control  
  
1.  En el Diseñador de Windows Forms, seleccione la región principal (inferior) de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
2.  En la ventana Propiedades, establezca la propiedad `BackColor` en blanco.  
  
3.  Haga doble clic en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>para abrir el Editor de código.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
4.  En el Editor de código, en la lista desplegable de eventos, haga clic en **DrawItem**.  
  
5.  En la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>el controlador de eventos, agregue el siguiente código para alternar la `BackColor`:</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>  
  
     [!code-cs[VbPowerPacksDataRepeaterWalkthrough&#1;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough n.º&1;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]  
  
6.  En la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>el controlador de eventos, agregue el código siguiente para cambiar la `ForeColor` de una etiqueta según una condición:</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>  
  
     [!code-cs[VbPowerPacksDataRepeaterWalkthrough&#2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]  
  
7.  Presione F5 para ejecutar la aplicación y ver las personalizaciones.  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a>Impedir que los usuarios agreguen o eliminen registros  
 En este paso opcional, agregará código que impide que los usuarios agreguen o eliminen registros en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a>Para impedir que los usuarios agreguen y eliminen registros  
  
1.  En el Diseñador de Windows Forms, haga doble clic en el formulario para abrir el Editor de código.  
  
2.  Agregue el código siguiente al evento `Form_Load` :  
  
     [!code-cs[VbPowerPacksDataRepeaterWalkthrough&3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]  
  
3.  En la lista desplegable Nombre de clase, haga clic en **BindingNavigatorDeleteItem**. En la lista desplegable Nombre de método, haga clic en **EnabledChanged**.  
  
4.  Agregue el código siguiente al controlador de eventos `BindingNavigatorDeleteItem_EnabledChanged` :  
  
     [!code-cs[VbPowerPacksDataRepeaterWalkthrough Nº&4;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&#4;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]  
  
    > [!NOTE]
    >  Este paso es necesario porque el <xref:System.Windows.Forms.BindingSource>habilitará la **DeleteItem** botón cada vez que cambie el registro actual.</xref:System.Windows.Forms.BindingSource>  
  
5.  Presione F5 para ejecutar la aplicación. Observe que el botón **DeleteItem** está deshabilitado y que no se pueden eliminar elementos presionando la tecla Supr.  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a>Agregar capacidad de búsqueda al control DataRepeater  
 En este paso opcional, implementa la capacidad de buscar un valor en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Si se encuentra la cadena de búsqueda, el control selecciona el elemento que contiene el valor y desplaza el elemento en la vista.  
  
#### <a name="to-add-search-capability"></a>Para agregar capacidad de búsqueda  
  
1.  Arrastre un <xref:System.Windows.Forms.TextBox>control desde el **herramientas** hasta el formulario que contiene el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:System.Windows.Forms.TextBox>  
  
     Colóquelo bajo el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
2.  En la ventana Propiedades, cambie la propiedad **Name** a **SearchTextBox**.  
  
3.  Arrastre un <xref:System.Windows.Forms.Button>control desde el **herramientas** hasta el formulario que contiene el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:System.Windows.Forms.Button> Colóquelo bajo el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
4.  En la ventana Propiedades, cambie la propiedad **Name** a **SearchButton**. Cambie la propiedad **Text** a **Search**.  
  
5.  Haga doble clic en el <xref:System.Windows.Forms.Button>control para abrir el Editor de código y agregue el código siguiente a la `SearchButton_Click` controlador de eventos.</xref:System.Windows.Forms.Button>  
  
     [!code-cs[VbPowerPacksDataRepeaterWalkthrough&#5;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&#5;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]  
  
6.  Presione F5 para ejecutar la aplicación. Escriba un identificador de cliente en **SearchTextBox** y haga clic en el botón **Buscar** .  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a>Agregar una tabla maestra y de detalles a DataRepeater  
 En este paso opcional, agrega una segunda <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control para mostrar los pedidos relacionados para cada cliente.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
#### <a name="to-add-a-master-and-detail-table"></a>Para agregar una tabla maestra y de detalles  
  
1.  Arrastre una segunda <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control desde el **Visual Basic PowerPacks** ficha en el **herramientas** hasta el formulario.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
2.  En la ventana Propiedades, establezca la propiedad **Location** en `465, 25`.  
  
3.  Establezca la propiedad **Size** en `315, 600`.  
  
4.  En la ventana **Orígenes de datos** , expanda el nodo de la tabla **Customers** y seleccione el nodo de detalle de la tabla **Orders** .  
  
5.  Cambie el tipo de colocación de esta tabla **Orders** a Detalles haciendo clic en **Detalles** en la lista desplegable del nodo de la tabla.  
  
6.  Arrastre esto **pedidos** a la región de plantilla de elementos (la región superior) del segundo nodo de la tabla <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
     Se agregan un componente **OrdersBindingSource** y un componente **OrdersTableAdapter** a la bandeja de componentes.  
  
7.  Presione F5 para ejecutar la aplicación. Al seleccionar cada cliente en la primera <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controlar los pedidos de ese cliente se muestran en el segundo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="see-also"></a>Vea también  
 [Introducción al Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Cómo: mostrar los datos enlazados en un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [Cómo: mostrar controles no enlazados en un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [Cómo: cambiar el diseño de un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)   
 [Cómo: mostrar los encabezados de elemento en un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)   
 [Cómo: buscar datos en un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)   
 [Cómo: crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)   
 [Cómo: cambiar la apariencia de un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Cómo: deshabilitar, agregar y eliminar elementos DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)   
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
