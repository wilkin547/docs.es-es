---
title: Procedimiento Generar manualmente clases del servicio de datos del cliente (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: f8d99213a1ef98c48855ba9f561f87a800768c89
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894300"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a>Procedimiento Generar manualmente clases del servicio de datos del cliente (WCF Data Services)
WCF Data Services se integra con Visual Studio para permitir la generación automática de las clases del servicio de datos del cliente cuando se usa el cuadro de diálogo **Agregar referencia de servicio** para agregar una referencia a un servicio de datos en un proyecto de Visual Studio. Para obtener más información, consulte [Cómo Agregue una referencia](how-to-add-a-data-service-reference-wcf-data-services.md)de servicio de datos. También puede generar manualmente las mismas clases del servicio de datos del cliente mediante la herramienta de generación de código `DataSvcUtil.exe`. Esta herramienta, que se incluye con WCF Data Services, genera clases de .NET Framework a partir de la definición del servicio de datos. También se puede usar para generar clases del servicio de datos a partir del archivo de modelo conceptual (.csdl) y del archivo .edmx que representa un modelo de Entity Framework en un proyecto Visual Studio.

 El ejemplo usado en este tema crea clases del servicio de datos del cliente basadas en el servicio de datos de ejemplo de Northwind. Este servicio se crea cuando se completa la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md). Algunos ejemplos de este tema requieren el archivo de modelo conceptual para el modelo de Northwind. Para obtener más información, consulte [Cómo Use EdmGen. exe para generar los archivos](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)de asignación y de modelo. Algunos ejemplos de este tema requieren el archivo de modelo conceptual .edmx para el modelo de Northwind. Para obtener más información, vea [información general sobre el archivo. edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).

### <a name="to-generate-c-classes-that-support-data-binding"></a>Para generar clases de C# que admitan el enlace de datos

- En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a>Para generar clases Visual Basic que admitan el enlace de datos

- En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.

### <a name="to-generate-c-classes-based-on-the-service-uri"></a>Para generar clases de C# basadas en el URI de servicio

- En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a>Para generar clases de Visual Basic basadas en el URI de servicio

- En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a>Para generar clases de C# basadas en el archivo de modelo conceptual (CSDL)

- En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a>Para generar clases de Visual Basic basadas en el archivo de modelo conceptual (CSDL)

- En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a>Para generar clases de C# basadas en el archivo .edmx

- En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a>Para generar clases de Visual Basic basadas en el archivo .edmx

- En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a>Vea también

- [Generar la biblioteca cliente del servicio de datos](generating-the-data-service-client-library-wcf-data-services.md)
- [Cómo: Agregar una referencia de servicio de datos](how-to-add-a-data-service-reference-wcf-data-services.md)
- [Utilidad del cliente de servicio de datos de WCF (DataSvcUtil.exe)](wcf-data-service-client-utility-datasvcutil-exe.md)
