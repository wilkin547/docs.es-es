---
title: Crear una tabla de búsqueda con el componente BindingSource
ms.date: 03/30/2017
helpviewer_keywords:
- lookup tables
- tables [Windows Forms], creating lookup tables
- BindingSource component [Windows Forms], creating a lookup table
- BindingSource component [Windows Forms], examples
ms.assetid: 622fce80-879d-44be-abbf-8350ec22ca2b
ms.openlocfilehash: ccf2bfa6cf3f56a38b55f8c87004c42a46172891
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736812"
---
# <a name="how-to-create-a-lookup-table-with-the-windows-forms-bindingsource-component"></a>Cómo: Crear una tabla de búsqueda con el componente BindingSource de formularios Windows Forms
Una tabla de búsqueda es una tabla de datos con una columna que muestra los datos de los registros de una tabla relacionada. En los procedimientos siguientes se usa un control <xref:System.Windows.Forms.ComboBox> para mostrar el campo con la relación de clave externa desde la tabla primaria a la tabla secundaria.  
  
 Aquí se ofrece un ejemplo de una tabla primaria y una tabla secundaria para ayudar a visualizar estas dos tablas y su relación:  
  
 CustomersTable (tabla primaria)  
  
|CustomerID|CustomerName|  
|----------------|------------------|  
|712|Paul Koch|  
|713|Tamara Johnston|  
  
 OrdersTable (tabla secundaria)  
  
|OrderID|OrderDate|CustomerID|  
|-------------|---------------|----------------|  
|903|12.02.04|712|  
|904|13.02.04|713|  
  
 En este escenario, una tabla, CustomersTable, almacena la información real que quiere mostrar y guardar. Pero, para ahorrar espacio, la tabla deja fuera los datos que aportan claridad. La otra tabla, OrdersTable, contienen solo la información relativa al aspecto sobre qué número de identificación de cliente equivale a qué fecha de pedido e identificador de pedido. No hay ninguna mención a los nombres de los clientes.  
  
 En el control [ComboBox Control](combobox-control-windows-forms.md) se establecen cuatro propiedades importantes para crear la tabla de búsqueda.  
  
- La propiedad <xref:System.Windows.Forms.ComboBox.DataSource%2A> contiene el nombre de la tabla.  
  
- La propiedad <xref:System.Windows.Forms.ListControl.DisplayMember%2A> contiene la columna de datos de esa tabla que quiere mostrar para el texto del control (nombre del cliente).  
  
- La propiedad <xref:System.Windows.Forms.ListControl.ValueMember%2A> contiene la columna de datos de esa con la información almacenada (número de identificación en la tabla primaria).  
  
- La propiedad <xref:System.Windows.Forms.ListControl.SelectedValue%2A> proporciona el valor de búsqueda de la tabla secundaria, basado en <xref:System.Windows.Forms.ListControl.ValueMember%2A>.  
  
 Los procedimientos siguientes muestran cómo diseñar el formulario como una tabla de búsqueda y enlazar datos a controles en ella. Para realizar correctamente los procedimientos, debe tener un origen de datos con tablas primarias y secundarias que tengan una relación de clave externa, tal y como se indicó anteriormente.  
  
### <a name="to-create-the-user-interface"></a>Para crear la interfaz de usuario  
  
1. En el **cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.ComboBox> al formulario.  
  
     Este control mostrará la columna de la tabla primaria.  
  
2. Arrastre otros controles para mostrar detalles de la tabla secundaria. El formato de los datos en la tabla debe determinar qué controles elegirá. Para más información, consulte [Controles de Windows Forms por función](windows-forms-controls-by-function.md).  
  
3. Arrastre un control <xref:System.Windows.Forms.BindingNavigator> al formulario; esto le permitirá navegar por los datos de la tabla secundaria.  
  
### <a name="to-connect-to-the-data-and-bind-it-to-controls"></a>Para conectar con los datos y enlazarlos a controles  
  
1. Seleccione el <xref:System.Windows.Forms.ComboBox> y haga clic en el glifo Tarea inteligente para mostrar el cuadro de diálogo Tarea inteligente.  
  
2. Seleccione **Usar elementos enlazados a datos**.  
  
3. Haga clic en la flecha junto al cuadro desplegable **Origen de datos**. Si ya se ha configurado un origen de datos para el proyecto o formulario, aparecerá; de lo contrario, realice los pasos siguientes. (En este ejemplo se usan las tablas Customers y Orders de la base de datos de muestra Northwind y se hace referencia a ellas entre paréntesis).  
  
    1. Haga clic en **Agregar origen de datos del proyecto** para conectar con los datos y crear un origen de datos.  
  
    2. En la página principal del **Asistente para la configuración de orígenes de datos**, haga clic en **Siguiente**.  
  
    3. Seleccione **Base de datos** en la página **Elegir un tipo de origen de datos**.  
  
    4. Seleccione una conexión de datos en la lista de conexiones disponibles, en la página **Elegir la conexión de datos**. Si los datos que quiere no están disponibles, seleccione **Nueva conexión** para crear una nueva conexión de datos.  
  
    5. Haga clic en **Sí, guardar la conexión** para guardar la cadena de conexión en el archivo de configuración de la aplicación.  
  
    6. Seleccione los objetos de base de datos que va a traer a su aplicación. En este caso, seleccione una tabla primaria y una tabla secundaria (por ejemplo, Customers y Orders) con una relación de clave externa.  
  
    7. Reemplace el nombre del conjunto de datos predeterminado, si lo desea.  
  
    8. Haga clic en **Finalizar**.  
  
4. En el cuadro desplegable **Mostrar miembro**, seleccione el nombre de la columna (por ejemplo, ContactName) que se mostrará en el cuadro combinado.  
  
5. En el cuadro desplegable **Miembro de valor**, seleccione la columna (por ejemplo, CustomerID) para realizar la operación de búsqueda en la tabla secundaria.  
  
6. En el cuadro desplegable **Valor seleccionado**, navegue a **Orígenes de datos del proyecto** y al conjunto de datos recién creado que contiene las tablas primaria y secundaria. Seleccione la misma propiedad de la tabla secundaria que sea el Miembro de valor de la tabla primaria (por ejemplo, Orders.CustomerID). Se crearán el <xref:System.Windows.Forms.BindingSource>, el conjunto de datos y los componentes de adaptador de tabla correspondientes, y se agregarán al formulario.  
  
7. Enlace el control <xref:System.Windows.Forms.BindingNavigator> al <xref:System.Windows.Forms.BindingSource> de la tabla secundaria (por ejemplo, `OrdersBindingSource`).  
  
8. Enlace otros controles, aparte de <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.BindingNavigator>, a los campos de detalles del <xref:System.Windows.Forms.BindingSource> de la tabla secundaria (por ejemplo, `OrdersBindingSource`) que quiera mostrar.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.BindingSource>
- [Componente BindingSource](bindingsource-component.md)
- [ComboBox (control)](combobox-control-windows-forms.md)
- [Enlazar controles a los datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
