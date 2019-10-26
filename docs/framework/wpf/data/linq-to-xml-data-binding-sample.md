---
title: Ejemplo de enlace de datos de LINQ to XML
ms.date: 10/22/2019
ms.topic: sample
helpviewer_keywords:
- linq to xml data binding sample
ms.openlocfilehash: aac814e4768a863a93e69e34cd18c941a9b35c89
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921225"
---
# <a name="linq-to-xml-data-binding-sample"></a>Ejemplo de enlace de datos de LINQ to XML

En este artículo se describe el ejemplo LinqToXmlDataBinding, una aplicación Windows Presentation Foundation (WPF) que enlaza los componentes de la interfaz de usuario a un origen de datos XML incrustado.

## <a name="overview"></a>Información general

El ejemplo LinqToXmlDataBinding es una aplicación Windows Presentation Foundation (WPF) que contiene C# archivos de código fuente XAML y. Un documento XML incrustado define una lista de libros. La aplicación permite al usuario ver, agregar, eliminar y editar las entradas del libro.

Hay dos archivos de origen principales:

- [L2DBForm.xaml](l2dbform-xaml-source-code.md) contiene el código de declaración XAML para la interfaz de usuario (IU) de la ventana principal. También contiene una sección de recursos de ventana que define un proveedor de datos y un documento XML incrustado para los listados de libros.

- [L2DBForm.xaml.cs](l2dbform-xaml-cs-source-code.md) contiene los métodos de control de eventos y de inicialización asociados a la IU.

La ventana principal se divide en las cuatro secciones de IU verticales siguientes:

- **XML** muestra el origen XML sin procesar de la lista de libros insertada.

- **Lista de libros** muestra las entradas de libro como texto estándar y permite que el usuario seleccione y elimine entradas individuales.

- **Edit Selected Book** (Editar libro seleccionado) permite que el usuario edite los valores asociados a la entrada de libro seleccionada actualmente.

- **Add New Book** (Agregar nuevo libro) permite la creación de una entrada de libro según los valores especificados por el usuario.

## <a name="run-the-sample"></a>Ejecutar el ejemplo

En esta sección se muestra cómo crear y compilar el proyecto LinqToXmlDataBinding en Visual Studio y cómo ejecutar la aplicación LinqToXmlDataBinding Windows Presentation Foundation (WPF) resultante.

### <a name="create-the-project"></a>Crear el proyecto

1. Abra Visual Studio y cree una **aplicación WPF** de C# con el nombre **LinqToXmlDataBinding**.

   El proyecto debe tener como destino .NET Framework3.5 (o posterior).

1. Si aún no están presentes, agregue referencias al proyecto para los siguientes ensamblados de .NET:

    - System.Data
    - System.Data.DataSetExtensions
    - System.Xml
    - System.Xml

1. Compile la solución presionando **Ctrl**+**Mayús**+**B** y después presione **F5** para ejecutarla.

   El proyecto debería compilarse sin errores y ejecutarse como una aplicación WPF genérica.

### <a name="add-code"></a>Agregar código

1. En el **Explorador de soluciones**, cambie el nombre del archivo de origen **Window1.xaml** a **L2XDBForm.xaml**.

   El nombre del archivo de código fuente dependiente Window1.xaml.cs se cambia automáticamente a L2XDBForm.xaml.cs.

1. Reemplace el código fuente que se encuentra en el archivo **L2XDBForm. Xaml** por el [código fuente L2DBForm. Xaml](l2dbform-xaml-source-code.md). (Use la vista de origen de XAML para trabajar con este archivo).

1. Del mismo modo, reemplace el código fuente de **L2XDBForm.Xaml.CS** por el [código fuente de L2DBForm.Xaml.CS](l2dbform-xaml-cs-source-code.md).

1. En el archivo **app. Xaml**, reemplace todas las apariciones de la cadena **Window1. Xaml** por **L2XDBForm. Xaml**.

1. Compile la solución presionando **Ctrl**+**Mayús**+**B**.

### <a name="run-the-app"></a>Ejecutar la aplicación

La aplicación LinqToXmlDataBinding permite al usuario ver y manipular una lista de libros que se almacenan como un elemento XML incrustado. Ejecute la aplicación presionando **F5** (iniciar depuración) o **Ctrl**+**F5** (iniciar sin depurar).

Se muestra una ventana de programa con el título **Enlace de datos de WPF con LINQ to XML**.

La sección superior de la interfaz de usuario muestra el **XML** sin formato que representa la lista de libros. Se muestra mediante un control <xref:System.Windows.Controls.TextBlock> de WPF, que no permite la interacción a través del mouse o del teclado.

En la segunda sección vertical, con la etiqueta **Lista de libros**, se muestran los libros como una lista ordenada de texto sin formato. Utiliza un control <xref:System.Windows.Controls.ListBox> que permite la selección a través del mouse o del teclado.

### <a name="add-and-delete-books"></a>Agregar y eliminar libros

Para agregar un nuevo libro a la lista, escriba los valores en los controles **ID.** y **valor** <xref:System.Windows.Controls.TextBox> de la última sección, **Agregar nuevo libro**y, a continuación, seleccione **Agregar libro**. El libro se anexa a la lista en los listados de libros y XML. Este programa no valida los valores de entrada.

Para eliminar un libro existente de la lista, selecciónelo en la sección **lista de libros** y, a continuación, seleccione quitar el **libro seleccionado**. La entrada del libro se quita del libro y de las listas de origen XML sin formato.

### <a name="edit-a-book-entry"></a>Editar una entrada de libro

1. Seleccione la entrada del libro en la segunda sección **Lista de libros**.

   Sus valores actuales se muestran en la sección **editar el libro seleccionado** .

1. Edite los valores usando el teclado. Tan pronto como el control <xref:System.Windows.Controls.TextBox> pierde el foco, los cambios se propagan automáticamente a la lista de orígenes y libros de origen XML.
