---
title: 'Cómo: Generar manualmente clases del servicio de datos cliente (Servicios de datos de WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: 368f2546652d21be44c0ffb4cc5f279c56beda51
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165997"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a>Cómo: Generar manualmente clases del servicio de datos cliente (Servicios de datos de WCF)

WCF Data Services se integra con Visual Studio para permitir la generación automática de las clases del servicio de datos del cliente cuando se usa el cuadro de diálogo **Agregar referencia de servicio** para agregar una referencia a un servicio de datos en un proyecto de Visual Studio. Para obtener más información, vea [Cómo: agregar una referencia de servicio de datos](how-to-add-a-data-service-reference-wcf-data-services.md). También puede generar manualmente las mismas clases del servicio de datos del cliente mediante la herramienta de generación de código `DataSvcUtil.exe`. Esta herramienta, que se incluye con WCF Data Services, genera clases de .NET Framework a partir de la definición del servicio de datos. También se puede usar para generar clases del servicio de datos a partir del archivo de modelo conceptual (.csdl) y del archivo .edmx que representa un modelo de Entity Framework en un proyecto Visual Studio.

 El ejemplo usado en este tema crea clases del servicio de datos del cliente basadas en el servicio de datos de ejemplo de Northwind. Este servicio se crea cuando se completa la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md). Algunos ejemplos de este tema requieren el archivo de modelo conceptual para el modelo de Northwind. Para obtener más información, vea [Cómo: usar EdmGen.exe para generar los archivos de asignación y de modelo](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md). Algunos ejemplos de este tema requieren el archivo de modelo conceptual .edmx para el modelo de Northwind. Para obtener más información, vea [información general sobre el archivo. edmx](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).

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

## <a name="see-also"></a>Consulte también

- [Generar la biblioteca cliente del servicio de datos](generating-the-data-service-client-library-wcf-data-services.md)
- [Procedimiento para agregar una referencia a un servicio de datos](how-to-add-a-data-service-reference-wcf-data-services.md)
- [Utilidad del cliente de Servicio de datos de WCF (DataSvcUtil.exe)](wcf-data-service-client-utility-datasvcutil-exe.md)
