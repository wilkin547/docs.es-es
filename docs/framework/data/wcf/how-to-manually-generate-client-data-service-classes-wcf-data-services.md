---
title: "C&#243;mo: Generar manualmente clases del servicio de datos del cliente (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, biblioteca de cliente"
  - "WCF Data Services, configurar"
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# C&#243;mo: Generar manualmente clases del servicio de datos del cliente (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] se integra con Visual Studio para permitir la generación automática de las clases del servicio de datos del cliente cuando se usa el cuadro de diálogo **Agregar referencia de servicio** para agregar una referencia a un servicio de datos en un proyecto de Visual Studio.  Para obtener más información, consulta [Cómo: Agregar una referencia a un servicio de datos](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).  También puede generar manualmente las mismas clases de servicio de datos cliente mediante la herramienta de generación de código, `DataSvcUtil.exe`. Esta herramienta, que está incluida con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], genera clases de .NET Framework a partir de la definición del servicio de datos.  También se puede usar para generar clases del servicio de datos a partir del archivo de modelo conceptual \(.csdl\) y del archivo .edmx que representa un modelo de Entity Framework en un proyecto Visual Studio.  
  
 El ejemplo usado en este tema crea clases del servicio de datos del cliente basadas en el servicio de datos de ejemplo de Northwind.  Este servicio se crea cuando se completa el [Tutorial rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  Algunos ejemplos de este tema requieren el archivo de modelo conceptual para el modelo de Northwind.  Para obtener más información, consulta [Cómo: Usar EdmGen.exe para generar los archivos de asignación y de modelo](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  Algunos ejemplos de este tema requieren el archivo de modelo conceptual .edmx para el modelo de Northwind.  Para obtener más información, consulta [.edmx File Overview](http://msdn.microsoft.com/es-es/f4c8e7ce-1db6-417e-9759-15f8b55155d4).  
  
### Para generar clases de C\# que admitan el enlace de datos  
  
-   En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.  
  
### Para generar clases Visual Basic que admitan el enlace de datos  
  
-   En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.  
  
### Para generar clases de C\# basadas en el URI de servicio  
  
-   En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.  
  
### Para generar clases de Visual Basic basadas en el URI de servicio  
  
-   En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.  
  
### Para generar clases de C\# basadas en el archivo de modelo conceptual \(CSDL\)  
  
-   En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs  
    ```  
  
### Para generar clases de Visual Basic basadas en el archivo de modelo conceptual \(CSDL\)  
  
-   En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb  
    ```  
  
### Para generar clases de C\# basadas en el archivo .edmx  
  
-   En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs   
    ```  
  
### Para generar clases de Visual Basic basadas en el archivo .edmx  
  
-   En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb   
    ```  
  
## Vea también  
 [Generar la biblioteca de cliente del servicio de datos](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)   
 [Cómo: Agregar una referencia a un servicio de datos](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)   
 [Utilidad de cliente de WCF Data Service \(DataSvcUtil.exe\)](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)