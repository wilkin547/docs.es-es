---
description: Más información acerca de cómo crear la aplicación cliente de .NET Framework (inicio rápido de Servicios de datos de WCF)
title: Crear la aplicación cliente de .NET Framework (Inicio rápido de Data Services de WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: 6a397726b0680d4091f7cefd8928e43c74dc08bf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766232"
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a>Crear la aplicación cliente de .NET Framework (Inicio rápido de Data Services de WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Esta es la tarea final de la guía de inicio rápido de Servicios de datos de WCF. En esta tarea, agregará una aplicación de consola a la solución, agregará una referencia a la fuente de Open Data Protocol (OData) en esta nueva aplicación cliente y tendrá acceso a la fuente de OData desde la aplicación cliente mediante las bibliotecas de cliente y las clases de servicio de datos de cliente generadas.

> [!NOTE]
> No es necesaria una aplicación cliente basada en .NET Framework para obtener acceso a una fuente de datos. Cualquier componente de la aplicación que consume una fuente de OData puede tener acceso al servicio de datos. Para obtener más información, consulte [uso de un servicio de datos en una aplicación cliente](using-a-data-service-in-a-client-application-wcf-data-services.md).

## <a name="to-create-the-client-application-by-using-visual-studio"></a>Para crear la aplicación cliente mediante Visual Studio

1. En **Explorador de soluciones**, haga clic con el botón secundario en la solución, haga clic en **Agregar** y, a continuación, haga clic en **nuevo proyecto**.

2. En el panel izquierdo, seleccione **instalado** > [**Visual C#** o **Visual Basic**] > **escritorio de Windows** y, a continuación, seleccione la plantilla **aplicación WPF** .

3. Escriba `NorthwindClient` como nombre del proyecto y, a continuación, haga clic en **Aceptar**.

4. Abra el archivo MainWindow.xaml y reemplace el código XAML con el código siguiente:

     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml#window1xaml)]

## <a name="to-add-a-data-service-reference-to-the-project"></a>Para agregar al proyecto una referencia al servicio de datos

1. En **Explorador de soluciones**, haga clic con el botón secundario en el proyecto NorthwindClient, haga clic en **Agregar**  >  **referencia de servicio** y, a continuación, haga clic en **detectar**.

     De este modo se muestra el servicio de datos de Northwind que creó en la primera tarea.

2. En el cuadro de texto **espacio de nombres** , escriba `Northwind` y, a continuación, haga clic en **Aceptar**.

     De este modo se agrega un nuevo archivo de código al proyecto, que contiene las clases de datos que se usan para obtener acceso e interactuar con los recursos del servicio de datos como objetos. Las clases de datos se crean en el espacio de nombres `NorthwindClient.Northwind`.

## <a name="to-access-data-service-data-in-the-wpf-application"></a>Para tener acceso a los datos del servicio de datos en la aplicación WPF

1. En **Explorador de soluciones** en **NorthwindClient**, haga clic con el botón derecho en el proyecto y haga clic en **Agregar referencia**.

2. En el cuadro de diálogo **Agregar referencia** , haga clic en la pestaña **.net** , seleccione el ensamblado de System.Data.Services.Client.dll y, a continuación, haga clic en **Aceptar**.

3. En **Explorador de soluciones** en **NorthwindClient**, abra la página de códigos del archivo MainWindow. XAML y agregue la instrucción siguiente `using` ( `Imports` en Visual Basic).

    [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#using)]
    [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#using)]

4. Inserte el código siguiente que consulta al servicio de datos y enlaza el resultado a una instancia de <xref:System.Data.Services.Client.DataServiceCollection%601> en la clase `MainWindow`:

    > [!NOTE]
    > Debe reemplazar el nombre de host `localhost:12345` por el servidor y el puerto en que se hospeda la instancia del servicio de datos de Northwind.

     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#querycode)]

5. Inserte el código siguiente que guarda los cambios en la clase `MainWindow`:

     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#savechanges)]

## <a name="to-build-and-run-the-northwindclient-application"></a>Para compilar y ejecutar la aplicación NorthwindClient

1. En **Explorador de soluciones**, haga clic con el botón derecho en el proyecto NorthwindClient y seleccione **establecer como proyecto de inicio**.

2. Presione **F5** para iniciar la aplicación.

     Se compila la solución y se inicia la aplicación cliente. Los datos se solicitarán al servicio y se mostrarán en la consola.

3. Edite un valor en la columna **Quantity** de la cuadrícula de datos y, a continuación, haga clic en **Guardar**.

     Los cambios se guardan en el servicio de datos.

    > [!NOTE]
    > Esta versión de la aplicación NorthwindClient no admite agregar ni eliminar entidades.

## <a name="next-steps"></a>Pasos siguientes

Ha creado correctamente la aplicación cliente que tiene acceso a la fuente de OData de ejemplo Northwind. También ha completado el tutorial de inicio rápido de Servicios de datos de WCF.

Para obtener más información sobre el acceso a una fuente de OData desde una aplicación .NET Framework, consulte [servicios de datos de WCF biblioteca de cliente](wcf-data-services-client-library.md).

## <a name="see-also"></a>Vea también

- [Introducción](getting-started-with-wcf-data-services.md)
- [Recursos](wcf-data-services-resources.md)
