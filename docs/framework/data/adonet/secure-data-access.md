---
title: "Acceso seguro a datos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 473ebd69-21a3-4627-b95e-4e04d035c56f
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Acceso seguro a datos
Para escribir código de ADO.NET seguro, debe comprender los mecanismos de seguridad disponibles en el almacén de datos subyacente o en la base de datos.  También debe tener en cuenta las implicaciones en la seguridad de otras características o componentes que pudieran incluirse en la aplicación.  
  
## Autenticación, autorización y permisos  
 Si se conecta a Microsoft SQL Server, puede usar la autenticación de Windows, también conocida como seguridad integrada, que emplea la identidad del usuario de Windows activo en lugar de pasar un identificador de usuario y una contraseña.  Se recomienda encarecidamente usar la autenticación de Windows, ya que las credenciales del usuario no están expuestas en la cadena de conexión.  Si no puede usar la autenticación de Windows para conectarse a SQL Server, puede crear cadenas de conexión en tiempo de ejecución mediante <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.  
  
 Las credenciales utilizados para la autenticación deben tratarse de manera diferente dependiendo del tipo de aplicación.  Por ejemplo, en una aplicación de Windows Forms, se puede solicitar al usuario que proporcione información de autenticación o bien, se pueden utilizar las credenciales de Windows del usuario.  Sin embargo, una aplicación web normalmente obtiene acceso a los datos mediante credenciales proporcionadas por la misma aplicación y no por el usuario.  
  
 Una vez que los usuarios se han autenticado, el ámbito de sus acciones depende de los permisos que se les hayan concedido.  Siga siempre el principio de los privilegios mínimos y conceda solo los permisos absolutamente necesarios.  
  
 Para obtener más información, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|-------------|-----------------|  
|[Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)|Describe las prácticas y técnicas recomendadas de seguridad para proteger la información de conexión, como el uso de configuración protegida para cifrar cadenas de conexión.|  
|[Recommendations for Data Access Strategies](http://msdn.microsoft.com/es-es/72411f32-d12a-4de8-b961-e54fca7faaf5)|Proporciona recomendaciones para obtener acceso a datos y realizar operaciones de base de datos.|  
|[Compiladores de cadenas de conexión](../../../../docs/framework/data/adonet/connection-string-builders.md)|Describe cómo crear cadenas de conexión a partir de la entrada del usuario en tiempo de ejecución.|  
|[Información general sobre seguridad de SQL Server](../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)|Describe la arquitectura de seguridad de SQL Server.|  
  
## Comandos con parámetros e inyección de código SQL  
 La utilización de comandos con parámetros ayuda en la protección contra ataques por inyección de código SQL, en los que un atacante "inyecta" un comando en una instrucción SQL que pone en peligro la seguridad del servidor.  Los comandos con parámetros protegen de ataques por inyección de código SQL ya que garantizan que los valores recibidos desde un origen externo pasan solo como valores y no como parte de la instrucción de Transact\-SQL.  Como resultado, los comandos Transact\-SQL insertados en un valor no se ejecutan en el origen de datos.  En cambio, se evalúan únicamente como un valor de parámetro.  Además de las ventajas en el aspecto de la seguridad, los comandos con parámetros proporcionan un método práctico para organizar los valores que se pasan con una instrucción de Transact\-SQL a un procedimiento almacenado.  
  
 Para obtener más información sobre el uso de comandos con parámetros, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|-------------|-----------------|  
|[Parámetros DataAdapter](../../../../docs/framework/data/adonet/dataadapter-parameters.md)|Describe cómo usar parámetros con `DataAdapter`.|  
|[Modificar datos con procedimientos almacenados](../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)|Describe cómo especificar parámetros y cómo obtener un valor devuelto.|  
|[Administrar permisos con procedimientos almacenados en SQL Server](../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)|Describe cómo usar procedimientos almacenados de SQL Server para encapsular el acceso a datos.|  
  
## Ataques mediante scripts  
 Los ataques mediante scripts constituyen otra forma de inyección que usa caracteres malintencionados insertados en una página web.  El explorador no valida los caracteres insertados y los procesa como parte de la página.  
  
 Para obtener más información, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|-------------|-----------------|  
|[Script Exploits Overview](../Topic/Script%20Exploits%20Overview.md)|Describe cómo protegerse de ataques mediante scripts o instrucciones SQL.|  
  
## Ataques mediante sondeo  
 Es muy frecuente que los atacantes utilicen la información de una excepción, como el nombre del servidor, de la base de datos o de una tabla, para llevar a cabo un ataque contra el sistema.  Como las excepciones pueden contener información específica sobre la aplicación o el origen de datos, puede mejorar la protección de la aplicación y del origen de datos exponiendo únicamente la información necesaria al cliente.  
  
 Para obtener más información, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|-------------|-----------------|  
|[Fundamentos del control de excepciones](../../../../docs/standard/exceptions/exception-handling-fundamentals.md)|Describe las formas básicas Try\/Catch\/Finally del control de excepciones estructurado.|  
|[Procedimientos recomendados para excepciones](../../../../docs/standard/exceptions/best-practices-for-exceptions.md)|Describe los procedimientos recomendados para controlar excepciones.|  
  
## Proteger orígenes de datos de Access y Excel de Microsoft  
 Microsoft Access y Microsoft Excel pueden funcionar como almacén de datos para una aplicación de ADO.NET cuando los requisitos de seguridad son mínimos o no existen.  Sus características de seguridad son eficaces para fines de disuasión, aunque solo es conveniente confiar en ellas para evitar la intromisión por parte de usuarios no informados.  Los archivos de datos físicos de Access y Excel existen en el sistema de archivos y todos los usuarios deben tener acceso a ellos.  Esto los hace vulnerables ante ataques que pueden dar lugar al robo o pérdida de datos, ya que los archivos se pueden copiar o modificar fácilmente.  Cuando sea necesaria una seguridad potente, use SQL Server u otra base de datos basada en servidor donde los archivos de datos físicos no se puedan leer desde el sistema de archivos.  
  
 Para obtener más información sobre la protección de datos de Access y Excel, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|-------------|-----------------|  
|[Guía y consideraciones de seguridad para Access 2007](http://go.microsoft.com/fwlink/?LinkId=98354)|Describe técnicas de seguridad para Access 2007 como el cifrado de archivos, la administración de contraseñas, la conversión de bases de datos a los nuevos formatos ACCDB y ACCDE y el uso de otras opciones de seguridad.|  
|[Ayuda acerca de cómo proteger una base de datos de Access con el nivel de seguridad de usuario \(MDB\)](http://go.microsoft.com/fwlink/?LinkId=47697)|Se aplica a Access 2003.  Proporciona instrucciones para implementar la seguridad a nivel de usuario a fin de proteger los datos en Access 2003.|  
|[Descripción del rol de los archivos de información de grupo de trabajo en la seguridad de Access](http://support.microsoft.com/kb/305542)|Explica la función y la relación del archivo de información de grupo de trabajo en la seguridad de Access 2003.|  
|[Preguntas más frecuentes acerca de la seguridad de Microsoft Access para las versiones de Microsoft Access de la 2.0 a la 2000](http://go.microsoft.com/fwlink/?LinkId=47698)|Versión descargable de las preguntas más frecuentes sobre seguridad en Microsoft Access.|  
|[Solución de problemas relacionados con la seguridad y la protección](http://go.microsoft.com/fwlink/?LinkId=47703)|Ofrece soluciones a los problemas de seguridad más comunes en Excel 2003.|  
  
## Enterprise Services  
 COM\+ incluye su propio modelo de seguridad que se basa en las cuentas de Windows NT y en la suplantación de procesos y subprocesos.  El espacio de nombres <xref:System.EnterpriseServices> proporciona contenedores que permiten a las aplicaciones .NET integrar código administrado con servicios de seguridad COM\+ mediante la clase <xref:System.EnterpriseServices.ServicedComponent>.  
  
 Para obtener más información, vea el siguiente recurso.  
  
|Recurso|Descripción|  
|-------------|-----------------|  
|[COM\+ Role\-Based Security and the .NET Framework](http://msdn.microsoft.com/es-es/02ab22ef-e5e2-4d29-b33a-6e03d94c4981)|Describe cómo integrar código administrado en servicios de seguridad COM\+.|  
  
## Interoperar con código no administrado  
 .NET Framework proporciona interacción con código no administrado, incluidos componentes COM, servicios COM\+, bibliotecas de tipos externas y muchos servicios del sistema operativo.  El trabajo con código no administrado supone traspasar el perímetro de seguridad del código administrado.  Tanto su código como cualquier otro código que llame a su código, deben tener el permiso de código no administrado \(<xref:System.Security.Permissions.SecurityPermission> con el marcador <xref:System.Security.Permissions.SecurityPermissionFlag> especificado\).  El código no administrado puede insertar de forma involuntaria vulnerabilidades de seguridad en la aplicación.  Por tanto, debe evitar la interoperabilidad con código no administrado a menos que sea absolutamente necesario.  
  
 Para obtener más información, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|-------------|-----------------|  
|[Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md)|Contiene temas que describen cómo exponer componentes COM a .NET Framework y cómo exponer componentes de .NET Framework a COM.|  
|[Advanced COM Interoperability](http://msdn.microsoft.com/es-es/3ada36e5-2390-4d70-b490-6ad8de92f2fb)|Contiene temas avanzados como, por ejemplo, los ensamblados de interoperabilidad principal, los subprocesos y el cálculo de referencias personalizado.|  
  
## Vea también  
 [Proteger aplicaciones de ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)   
 [Seguridad en SQL Server](../../../../docs/framework/data/adonet/sql/sql-server-security.md)   
 [Recommendations for Data Access Strategies](http://msdn.microsoft.com/es-es/72411f32-d12a-4de8-b961-e54fca7faaf5)   
 [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)   
 [Compiladores de cadenas de conexión](../../../../docs/framework/data/adonet/connection-string-builders.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)