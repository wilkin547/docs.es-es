---
title: 'Cómo: Crear un servicio de datos utilizando un origen de datos de ADO.NET Entity Framework (Data Services de WCF)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: 1e559488a3260fafe6c211ff47226a258fc1289a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557702"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a>Cómo: Crear un servicio de datos utilizando un origen de datos de ADO.NET Entity Framework (Data Services de WCF)

WCF Data Services expone los datos de entidad como un servicio de datos. El marco de trabajo ADO. NETEntity proporciona estos datos de entidad cuando el origen de datos es una base de datos relacional. En este tema se muestra cómo crear un modelo de datos basado en Entity Framework en una aplicación web de Visual Studio que está basada en una base de datos existente y cómo usar este modelo de datos para crear un nuevo servicio de datos.

Entity Framework también proporciona una herramienta de línea de comandos que puede generar un modelo de Entity Framework fuera de un proyecto de Visual Studio. Para obtener más información, vea [Cómo: usar EdmGen.exe para generar los archivos de asignación y de modelo](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a>Para agregar un modelo de Entity Framework que está basado en una base de datos existente a una aplicación web existente

1. En el menú **proyecto** , haga clic en **Agregar**  >  **nuevo elemento**.

2. En el panel **plantillas** , haga clic en la categoría de **datos** y, a continuación, seleccione **ADO.NET Entity Data Model**.

3. Escriba el nombre del modelo y, a continuación, haga clic en **Agregar**.

     Se muestra la primera página del Asistente para Entity Data Model.

4. En el cuadro de diálogo **elegir contenido del modelo** , seleccione **generar desde la base de datos**. A continuación, haga clic en **Siguiente**.

5. Haga clic en el botón **nueva conexión** .

6. En el cuadro de diálogo **propiedades de conexión** , escriba el nombre del servidor, seleccione el método de autenticación, escriba el nombre de la base de datos y, a continuación, haga clic en **Aceptar**.

     El cuadro de diálogo **elegir la conexión de datos** se actualiza con la configuración de la conexión de la base de datos.

7. Asegúrese de que la casilla **Guardar configuración de conexión de entidad en App.Config como:** está activada. A continuación, haga clic en **Siguiente**.

8. En el cuadro de diálogo **Elija los objetos de base** de datos, seleccione todos los objetos de base de datos que va a exponer en el servicio de datos.

    > [!NOTE]
    > El servicio de datos no expone automáticamente los objetos incluidos en el modelo de datos. El propio servicio debe exponerlos explícitamente. Para obtener más información, vea [configurar el servicio de datos](configuring-the-data-service-wcf-data-services.md).

9. Haga clic en **Finalizar** para completar el asistente.

     Con esto se crea un modelo de datos predeterminado basado en una base de datos específica. Entity Framework permite personalizar el modelo de datos. Para obtener más información, vea [Entity Data Model herramientas tareas](/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a>Para crear el servicio de datos usando el nuevo modelo de datos

1. En Visual Studio, abra el archivo .edmx que representa el modelo de datos.

2. En el **Explorador de modelos**, haga clic con el botón derecho en el modelo, haga clic en **propiedades**y, a continuación, anote el nombre del contenedor de entidades.

3. En **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto ASP.net y, a continuación, haga clic en **Agregar**  >  **nuevo elemento**.

4. En el cuadro de diálogo **Agregar nuevo elemento** , seleccione la plantilla **servicio de datos de WCF** en la categoría **Web** .

   ![Plantilla de elemento de servicio de datos de WCF en Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > La plantilla de **servicio de datos de WCF** está disponible en visual Studio 2015, pero no en visual Studio 2017 o posterior.

5. Proporcione un nombre para el servicio y, a continuación, haga clic en **Aceptar**.

     Visual Studio crea los archivos de código y marcado XML para el nuevo servicio. De forma predeterminada, se abre la ventana del editor de código.

6. En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que hereda de la clase <xref:System.Data.Objects.ObjectContext> y que es el contenedor de entidades del modelo de datos, que anotó en el paso 2.

7. En el código del servicio de datos, permita a los clientes autorizados tener acceso a los conjuntos de entidades que expone el servicio de datos. Para obtener más información, vea [crear el servicio de datos](creating-the-data-service.md).

8. Para probar el servicio de datos Northwind. SVC mediante un explorador Web, siga las instrucciones del tema [acceso al servicio desde un explorador Web](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).

## <a name="see-also"></a>Vea también

- [Definir Servicios de datos de WCF](defining-wcf-data-services.md)
- [Proveedores de Data Services](data-services-providers-wcf-data-services.md)
- [Procedimiento para crear un servicio de datos mediante el proveedor de reflexión](create-a-data-service-using-rp-wcf-data-services.md)
- [Procedimiento para crear un servicio de datos mediante un origen de datos de LINQ to SQL](create-a-data-service-using-linq-to-sql-wcf.md)
