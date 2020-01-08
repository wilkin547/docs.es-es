---
title: Acceso seguro a datos
ms.date: 03/30/2017
ms.assetid: 473ebd69-21a3-4627-b95e-4e04d035c56f
ms.openlocfilehash: ede8b1a2e840b56d6e7f45e6d26e09fa5e8bcc25
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337522"
---
# <a name="secure-data-access"></a>Acceso seguro a datos
Para escribir código de ADO.NET seguro, debe comprender los mecanismos de seguridad disponibles en el almacén de datos subyacente o en la base de datos. También debe tener en cuenta las implicaciones en la seguridad de otras características o componentes que pudieran incluirse en la aplicación.  
  
## <a name="authentication-authorization-and-permissions"></a>Autenticación, autorización y permisos  
 Si se conecta a Microsoft SQL Server, puede usar la autenticación de Windows, también conocida como seguridad integrada, que emplea la identidad del usuario de Windows activo en lugar de pasar un identificador de usuario y una contraseña. Se recomienda encarecidamente usar la autenticación de Windows, ya que las credenciales del usuario no están expuestas en la cadena de conexión. Si no puede usar la autenticación de Windows para conectarse a SQL Server, puede crear cadenas de conexión en tiempo de ejecución mediante <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.  
  
 Las credenciales utilizados para la autenticación deben tratarse de manera diferente dependiendo del tipo de aplicación. Por ejemplo, en una aplicación de Windows Forms, se puede solicitar al usuario que proporcione información de autenticación o bien, se pueden utilizar las credenciales de Windows del usuario. Sin embargo, una aplicación web normalmente obtiene acceso a los datos mediante credenciales proporcionadas por la misma aplicación y no por el usuario.  
  
 Una vez que los usuarios se han autenticado, el ámbito de sus acciones depende de los permisos que se les hayan concedido. Siga siempre el principio de los privilegios mínimos y conceda solo los permisos absolutamente necesarios.  
  
 Para obtener más información, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Proteger la información de conexión](protecting-connection-information.md)|Describe las prácticas y técnicas recomendadas de seguridad para proteger la información de conexión, como el uso de configuración protegida para cifrar cadenas de conexión.|  
|[Recomendaciones para las estrategias de acceso a datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/8fxztkff(v=vs.90))|Proporciona recomendaciones para obtener acceso a datos y realizar operaciones de base de datos.|  
|[Generadores de cadenas de conexión](connection-string-builders.md)|Describe cómo crear cadenas de conexión a partir de la entrada del usuario en tiempo de ejecución.|  
|[Información general sobre la seguridad de SQL Server](./sql/overview-of-sql-server-security.md)|Describe la arquitectura de seguridad de SQL Server.|  
  
## <a name="parameterized-commands-and-sql-injection"></a>Comandos con parámetros e inyección de código SQL  
 La utilización de comandos con parámetros ayuda en la protección contra ataques por inyección de código SQL, en los que un atacante "inyecta" un comando en una instrucción SQL que pone en peligro la seguridad del servidor. Los comandos con parámetros protegen de ataques por inyección de código SQL ya que garantizan que los valores recibidos desde un origen externo pasan solo como valores y no como parte de la instrucción de Transact-SQL. Como resultado, los comandos Transact-SQL insertados en un valor no se ejecutan en el origen de datos. En cambio, se evalúan únicamente como un valor de parámetro. Además de las ventajas en el aspecto de la seguridad, los comandos con parámetros proporcionan un método práctico para organizar los valores que se pasan con una instrucción de Transact-SQL a un procedimiento almacenado.  
  
 Para obtener más información sobre el uso de comandos con parámetros, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Parámetros de DataAdapter](dataadapter-parameters.md)|Describe cómo usar parámetros con `DataAdapter`.|  
|[Modificación de datos con procedimientos almacenados](modifying-data-with-stored-procedures.md)|Describe cómo especificar parámetros y cómo obtener un valor devuelto.|  
|[Administración de permisos con procedimientos almacenados en SQL Server](./sql/managing-permissions-with-stored-procedures-in-sql-server.md)|Describe cómo usar procedimientos almacenados de SQL Server para encapsular el acceso a datos.|  
  
## <a name="script-exploits"></a>Ataques mediante scripts  
 Los ataques mediante scripts constituyen otra forma de inyección que usa caracteres malintencionados insertados en una página web. El explorador no valida los caracteres insertados y los procesa como parte de la página.  
  
 Para obtener más información, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Introducción a los ataques de scripts](https://docs.microsoft.com/previous-versions/aspnet/w1sw53ds(v=vs.100))|Describe cómo protegerse de ataques mediante scripts o instrucciones SQL.|  
  
## <a name="probing-attacks"></a>Ataques mediante sondeo  
 Es muy frecuente que los atacantes utilicen la información de una excepción, como el nombre del servidor, de la base de datos o de una tabla, para llevar a cabo un ataque contra el sistema. Como las excepciones pueden contener información específica sobre la aplicación o el origen de datos, puede mejorar la protección de la aplicación y del origen de datos exponiendo únicamente la información necesaria al cliente.  
  
 Para obtener más información, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Controlar y generar excepciones en .NET](../../../standard/exceptions/index.md)|Describe las formas básicas Try/Catch/Finally del control de excepciones estructurado.|  
|[Procedimientos recomendados para excepciones](../../../standard/exceptions/best-practices-for-exceptions.md)|Describe los procedimientos recomendados para controlar excepciones.|  
  
## <a name="protecting-microsoft-access-and-excel-data-sources"></a>Proteger orígenes de datos de Access y Excel de Microsoft  
 Microsoft Access y Microsoft Excel pueden funcionar como almacén de datos para una aplicación de ADO.NET cuando los requisitos de seguridad son mínimos o no existen. Sus características de seguridad son eficaces para fines de disuasión, aunque solo es conveniente confiar en ellas para evitar la intromisión por parte de usuarios no informados. Los archivos de datos físicos de Access y Excel existen en el sistema de archivos y todos los usuarios deben tener acceso a ellos. Esto los hace vulnerables ante ataques que pueden dar lugar al robo o pérdida de datos, ya que los archivos se pueden copiar o modificar fácilmente. Cuando sea necesaria una seguridad potente, use SQL Server u otra base de datos basada en servidor donde los archivos de datos físicos no se puedan leer desde el sistema de archivos.  
  
 Para obtener más información sobre la protección de datos de Access y Excel, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Consideraciones de seguridad e instrucciones para el acceso 2007](https://docs.microsoft.com/previous-versions/office/developer/office-2007/bb421308(v=office.12))|Describe técnicas de seguridad para Access 2007 como el cifrado de archivos, la administración de contraseñas, la conversión de bases de datos a los nuevos formatos ACCDB y ACCDE y el uso de otras opciones de seguridad.|  
|[Introducción a Access 2010 Security](https://support.office.com/article/Introduction-to-Access-2010-security-CAE6D764-0318-4622-955F-68D9F186D6CA)|Proporciona información general sobre las características de seguridad que ofrece Access 2010.|  
## <a name="enterprise-services"></a>Enterprise Services  
 COM+ incluye su propio modelo de seguridad que se basa en las cuentas de Windows NT y en la suplantación de procesos y subprocesos. El espacio de nombres <xref:System.EnterpriseServices> proporciona contenedores que permiten a las aplicaciones .NET integrar código administrado con servicios de seguridad COM+ mediante la clase <xref:System.EnterpriseServices.ServicedComponent>.  
  
 Para obtener más información, vea el siguiente recurso.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Seguridad basada en roles](https://docs.microsoft.com/previous-versions/dotnet/netframework-1.1/s6y8k15h(v=vs.71))|Describe cómo integrar código administrado en servicios de seguridad COM+.|  
  
## <a name="interoperating-with-unmanaged-code"></a>Interoperar con código no administrado  
 .NET Framework proporciona interacción con código no administrado, incluidos componentes COM, servicios COM+, bibliotecas de tipos externas y muchos servicios del sistema operativo. El trabajo con código no administrado supone traspasar el perímetro de seguridad del código administrado. Tanto su código como cualquier otro código que llame a su código, deben tener el permiso de código no administrado (<xref:System.Security.Permissions.SecurityPermission> con el marcador <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> especificado). El código no administrado puede insertar de forma involuntaria vulnerabilidades de seguridad en la aplicación. Por tanto, debe evitar la interoperabilidad con código no administrado a menos que sea absolutamente necesario.  
  
 Para obtener más información, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Interoperating with Unmanaged Code](../../interop/index.md) (Interoperar con código no administrado)|Contiene temas que describen cómo exponer componentes COM a .NET Framework y cómo exponer componentes de .NET Framework a COM.|
|[Interoperabilidad COM avanzada](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))|Contiene temas avanzados como, por ejemplo, los ensamblados de interoperabilidad principal, los subprocesos y el cálculo de referencias personalizado.|

## <a name="see-also"></a>Vea también

- [Proteger aplicaciones de ADO.NET](securing-ado-net-applications.md)
- [Seguridad de SQL Server](./sql/sql-server-security.md)
- [Recomendaciones para las estrategias de acceso a datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/8fxztkff(v=vs.90))
- [Proteger la información de conexión](protecting-connection-information.md)
- [Generadores de cadenas de conexión](connection-string-builders.md)
- [Información general sobre ADO.NET](ado-net-overview.md)
