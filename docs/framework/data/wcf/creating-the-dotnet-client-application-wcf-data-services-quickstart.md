---
title: Crear la aplicación cliente de .NET Framework (Inicio rápido de Data Services de WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: 86ded7351d435b3a7077f0354d8a923b33a3f2b6
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43854962"
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a>Crear la aplicación cliente de .NET Framework (Inicio rápido de Data Services de WCF)

Se trata de la tarea final de la Guía de inicio rápido de WCF Data Services. En esta tarea, agregará una aplicación de consola a la solución, agregue una referencia a la [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] se envían a esta nueva aplicación de cliente y tener acceso a la fuente de la aplicación cliente mediante el uso de las clases de servicio de datos de cliente generado y bibliotecas de cliente de OData .

> [!NOTE]
> No es necesaria una aplicación cliente basada en .NET Framework para obtener acceso a una fuente de datos. Puede tener acceso al servicio de datos por cualquier componente de aplicación que consume una fuente de OData. Para obtener más información, consulte [mediante un servicio de datos en una aplicación cliente](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).

## <a name="to-create-the-client-application-by-using-visual-studio"></a>Para crear la aplicación cliente mediante Visual Studio

1.  En **el Explorador de soluciones**, haga clic en la solución, haga clic en **agregar**y, a continuación, haga clic en **nuevo proyecto**.

2.  En el panel izquierdo, seleccione **instalado** > [**Visual C#** o **Visual Basic**] > **Windows Desktop**y, a continuación, seleccione el **Aplicación WPF** plantilla.

3.  Escriba `NorthwindClient` para el nombre del proyecto y, a continuación, haga clic en **Aceptar**.

4.  Abra el archivo MainWindow.xaml y reemplace el código XAML con el código siguiente:

     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml#window1xaml)]

## <a name="to-add-a-data-service-reference-to-the-project"></a>Para agregar al proyecto una referencia al servicio de datos

1.  En **el Explorador de soluciones**, haga clic en el proyecto NorthwindClient, haga clic en **agregar** > **referencia de servicio**y, a continuación, haga clic en **Discover** .

     De este modo se muestra el servicio de datos de Northwind que creó en la primera tarea.

2.  En el **Namespace** cuadro de texto, escriba `Northwind`y, a continuación, haga clic en **Aceptar**.

     De este modo se agrega un nuevo archivo de código al proyecto, que contiene las clases de datos que se usan para obtener acceso e interactuar con los recursos del servicio de datos como objetos. Las clases de datos se crean en el espacio de nombres `NorthwindClient.Northwind`.

## <a name="to-access-data-service-data-in-the-wpf-application"></a>Para tener acceso a los datos del servicio de datos en la aplicación WPF

1.  En **el Explorador de soluciones** en **NorthwindClient**, haga clic en el proyecto y haga clic en **Agregar referencia**.

2.  En el **Agregar referencia** cuadro de diálogo, haga clic en el **.NET** , seleccione el ensamblado System.Data.Services.Client.dll y, a continuación, haga clic en **Aceptar**.

3. En **el Explorador de soluciones** en **NorthwindClient**, abra la página de códigos para el archivo MainWindow.xaml y agregue las siguientes `using` instrucción (`Imports` en Visual Basic).

     [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#using)]
     [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#using)]

3.  Inserte el código siguiente que consulta al servicio de datos y enlaza el resultado a una instancia de <xref:System.Data.Services.Client.DataServiceCollection%601> en la clase `MainWindow`:

    > [!NOTE]
    > Debe reemplazar el nombre de host `localhost:12345` por el servidor y el puerto en que se hospeda la instancia del servicio de datos de Northwind.

     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#querycode)]

4.  Inserte el código siguiente que guarda los cambios en la clase `MainWindow`:

     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#savechanges)]

## <a name="to-build-and-run-the-northwindclient-application"></a>Para compilar y ejecutar la aplicación NorthwindClient

1.  En **el Explorador de soluciones**, haga clic en el proyecto NorthwindClient y seleccione **establecer como proyecto de inicio**.

2.  Presione **F5** para iniciar la aplicación.

     Se compila la solución y se inicia la aplicación cliente. Los datos se solicitarán al servicio y se mostrarán en la consola.

3.  Modificar un valor en el **cantidad** columna de la cuadrícula de datos y, a continuación, haga clic en **guardar**.

     Los cambios se guardan en el servicio de datos.

    > [!NOTE]
    > Esta versión de la aplicación NorthwindClient no admite agregar ni eliminar entidades.

## <a name="next-steps"></a>Pasos siguientes

Ha creado correctamente la aplicación cliente que tiene acceso a la fuente de OData de Northwind de ejemplo. También ha completado la Guía de inicio rápido de WCF Data Services.

Para obtener más información sobre el acceso a OData fuente de distribución desde un [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] aplicación, consulte [biblioteca de cliente de WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md).

## <a name="see-also"></a>Vea también

- [Introducción](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
- [Recursos](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)
