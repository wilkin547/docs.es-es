---
description: 'Más información acerca de: consideraciones de seguridad (Entity Framework)'
title: Consideraciones de seguridad (Entity Framework)
ms.date: 03/30/2017
ms.assetid: 84758642-9b72-4447-86f9-f831fef46962
ms.openlocfilehash: fc09fa519d6f357e2f684fd5666b233081cd19fe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673276"
---
# <a name="security-considerations-entity-framework"></a>Consideraciones de seguridad (Entity Framework)

En este tema se describen las consideraciones de seguridad específicas para el desarrollo, la implementación y la ejecución de aplicaciones Entity Framework. También debe seguir las recomendaciones para crear aplicaciones de .NET Framework seguras. Para más información, consulte [Introducción a la seguridad](../security-overview.md).  
  
## <a name="general-security-considerations"></a>Consideraciones generales de seguridad  

 Las siguientes consideraciones de seguridad se aplican a todas las aplicaciones que utilizan el Entity Framework.  
  
#### <a name="use-only-trusted-data-source-providers"></a>Usar solo proveedores de orígenes de datos de confianza.  

 Para comunicarse con el origen de datos, un proveedor debe hacer lo siguiente:  
  
- Recibir la cadena de conexión del Entity Framework.  
  
- Traducir el árbol de comandos al lenguaje de consultas nativo del origen de datos.  
  
- Ensamblar y devolver los conjuntos de resultados.  
  
 Durante la operación de inicio de sesión, la información que se basa en la contraseña del usuario se pasa al servidor a través de las bibliotecas de red del origen de datos subyacente. Un proveedor malintencionado puede robar las credenciales del usuario, generar consultas malintencionadas o alterar el conjunto de resultados.  
  
#### <a name="encrypt-your-connection-to-protect-sensitive-data"></a>Cifrar la conexión para proteger los datos confidenciales.  

 El Entity Framework no controla directamente el cifrado de datos. Si los usuarios tienen acceso a los datos a través de una red pública, la aplicación debería establecer una conexión cifrada al origen de datos para aumentar la seguridad. Para obtener más información, consulte la documentación relacionada con la seguridad correspondiente al origen de datos. Para obtener una SQL Server origen de datos, vea [cifrar conexiones a SQL Server](/previous-versions/sql/sql-server-2008-r2/ms189067(v=sql.105)).  
  
#### <a name="secure-the-connection-string"></a>Proteger la cadena de conexión.  

 La protección del acceso al origen de datos es uno de los objetivos más importantes a la hora de proteger una aplicación. Una cadena de conexión presenta una vulnerabilidad potencial si no se protege o si se construye incorrectamente. Al almacenar la información de conexión en texto sin formato o conservarla en la memoria, se pone en riesgo todo el sistema. A continuación se enumeran métodos recomendados para proteger las cadenas de conexión:  
  
- Utilice la autenticación de Windows con un origen de datos de SQL Server.  
  
     Al utilizar la autenticación de Windows para conectarse a un origen de datos de SQL Server, la cadena de conexión no contiene información de contraseñas ni del inicio de sesión.  
  
- Cifre las secciones del archivo de configuración mediante una configuración protegida.  
  
     ASP.NET incluye una característica denominada configuración protegida, que permite cifrar la información confidencial en un archivo de configuración. Si bien se ha diseñado principalmente para ASP.NET, la configuración protegida también puede usarse para cifrar secciones de los archivos de configuración en aplicaciones Windows. Para obtener una descripción detallada de las nuevas capacidades de configuración protegida, vea [cifrar la información de configuración mediante la configuración protegida](/previous-versions/aspnet/53tyfkaw(v=vs.100)).  
  
- Almacene las cadenas de conexión en archivos de configuración protegidos.  
  
     Nunca debería incrustar las cadenas de conexión en el código fuente. Las cadenas de conexión también se pueden almacenar en archivos de configuración, lo que elimina la necesidad de incrustarlas en el código de la aplicación. De forma predeterminada, el Asistente para Entity Data Model almacena las cadenas de conexión en el archivo de configuración de la aplicación. Debe proteger este archivo para evitar el acceso no autorizado.  
  
- Utilice generadores de cadenas de conexión al crear dinámicamente las conexiones.  
  
     Si debe construir las cadenas de conexión en tiempo de ejecución, utilice la clase <xref:System.Data.EntityClient.EntityConnectionStringBuilder>. Esta clase de generador de cadenas ayuda a evitar los ataques de inyección en las cadenas de conexión validando y anulando la información de entrada no válida. Para obtener más información, vea [Cómo: compilar una cadena de conexión de EntityConnection](how-to-build-an-entityconnection-connection-string.md). Utilice también la clase de generador de cadenas adecuada para construir la cadena de conexión del origen de datos que forma parte de la cadena de conexión de Entity Framework. Para obtener información sobre los generadores de cadenas de conexión para los proveedores de ADO.NET, consulte [compiladores de cadenas de conexión](../connection-string-builders.md).  
  
 Para más información, consulte [Proteger la información de conexión](../protecting-connection-information.md).  
  
#### <a name="do-not-expose-an-entityconnection-to-untrusted-users"></a>No exponga EntityConnection a usuarios que no sean de confianza.  

 Un objeto <xref:System.Data.EntityClient.EntityConnection> expone la cadena de conexión de la conexión subyacente. Un usuario con acceso a un objeto <xref:System.Data.EntityClient.EntityConnection> también puede cambiar el <xref:System.Data.ConnectionState> de la conexión subyacente. La clase <xref:System.Data.EntityClient.EntityConnection> no es segura para la ejecución de subprocesos.  
  
#### <a name="do-not-pass-connections-outside-the-security-context"></a>No pase las conexiones fuera del contexto de seguridad.  

 Una vez establecida una conexión, no debe pasarla fuera del contexto de seguridad. Por ejemplo, un subproceso con permiso para abrir una conexión no debería almacenar la conexión en una ubicación global. Si la conexión está disponible en una ubicación global, otro subproceso malintencionado puede utilizar la conexión abierta sin que se le haya concedido ese permiso explícitamente.  
  
#### <a name="be-aware-that-logon-information-and-passwords-may-be-visible-in-a-memory-dump"></a>Sea consciente de que la información de inicio de sesión y de contraseñas puede estar visible en un volcado de memoria.  

 Cuando la información de contraseñas y del inicio de sesión del origen de datos se proporciona en la cadena de conexión, se mantiene en la memoria hasta que la recolección de elementos no utilizados reclama los recursos. Esto impide determinar el momento en que una cadena de contraseña deja de estar en la memoria. Si una aplicación se bloquea, un archivo de volcado de memoria puede contener información de seguridad importante y el usuario que ejecuta la aplicación y cualquier usuario con acceso administrativo al equipo puede ver dicho archivo. Utilice la autenticación de Windows para las conexiones con Microsoft SQL Server.  
  
#### <a name="grant-users-only-the-necessary-permissions-in-the-data-source"></a>Conceda a los usuarios únicamente los permisos necesarios en el origen de datos.  

 Los administradores de orígenes de datos solo deberían conceder a los usuarios los permisos que necesitan. Aunque [!INCLUDE[esql](../../../../../includes/esql-md.md)] no admite las instrucciones DML que modifican datos, como INSERT, UPDATE o DELETE, los usuarios todavía pueden tener acceso a la conexión al origen de datos. Un usuario malintencionado podría utilizar esta conexión para ejecutar instrucciones DML en el lenguaje nativo del origen de datos.  
  
#### <a name="run-applications-with-the-minimum-permissions"></a>Ejecute las aplicaciones con los permisos mínimos.  

 Cuando permite que una aplicación administrada se ejecute con permisos de plena confianza, el .NET Framework no limita el acceso de la aplicación al equipo. De esta forma se puede permitir que una vulnerabilidad de seguridad en la aplicación ponga en peligro a todo el sistema. Para utilizar la seguridad de acceso del código y otros mecanismos de seguridad en el .NET Framework, debe ejecutar las aplicaciones mediante permisos de confianza parcial y con el conjunto mínimo de permisos que se necesitan para permitir que la aplicación funcione. Los permisos de acceso del código siguientes son los permisos mínimos que necesita la aplicación Entity Framework:  
  
- <xref:System.Security.Permissions.FileIOPermission>: <xref:System.Security.Permissions.FileIOPermissionAccess.Write> para abrir los archivos de metadatos especificados o <xref:System.Security.Permissions.FileIOPermissionAccess.PathDiscovery> para buscar los archivos de metadatos en un directorio.  
  
- <xref:System.Security.Permissions.ReflectionPermission>: <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess> para admitir consultas de LINQ to Entities.  
  
- <xref:System.Transactions.DistributedTransactionPermission>: <xref:System.Security.Permissions.PermissionState.Unrestricted> para darse de alta en una <xref:System.Transactions><xref:System.Transactions.Transaction>.  
  
- <xref:System.Security.Permissions.SecurityPermission>: <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter> para serializar las excepciones utilizando la interfaz <xref:System.Runtime.Serialization.ISerializable>.  
  
- Permiso para abrir una conexión de base de datos y ejecutar comandos en la base de datos, como <xref:System.Data.SqlClient.SqlClientPermission> para una base de datos de SQL Server.  
  
 Para obtener más información, consulta [Code Access Security and ADO.NET](../code-access-security.md).  
  
#### <a name="do-not-install-untrusted-applications"></a>No instale aplicaciones que no sean de confianza.  

 El Entity Framework no aplica ningún permiso de seguridad e invocará cualquier código de objeto de datos proporcionado por el usuario en proceso, independientemente de si es de confianza o no. Asegúrese de que la autenticación y la autorización del cliente se llevan a cabo en el almacén de datos y en la aplicación.  
  
#### <a name="restrict-access-to-all-configuration-files"></a>Restrinja el acceso a todos los archivos de configuración.  

 Un administrador debe restringir el acceso de escritura a todos los archivos que especifican la configuración de una aplicación, incluidos enterprisesec.config, security.config, Machine. conf y el archivo de configuración de la aplicación \<*application*>.exe.config.  
  
 El nombre invariable del proveedor es modificable en el app.config. La aplicación cliente debe asumir la responsabilidad de tener acceso al proveedor subyacente a través del modelo de generador de proveedores estándar mediante un nombre seguro.  
  
#### <a name="restrict-permissions-to-the-model-and-mapping-files"></a>Restrinja los permisos a los archivos de asignación y de modelo.  

 Un administrador debe restringir el acceso de escritura a los archivos de asignación y de modelo (.edmx, .csdl, .ssdl y .msl) únicamente a los usuarios que modifican el modelo o las asignaciones. El Entity Framework solo requiere acceso de lectura a estos archivos en tiempo de ejecución. Además, un administrador debe restringir el acceso a los archivos de código fuente de la capa de objetos y la vista previamente compilada generados por las herramientas de Entity Data Model.  
  
## <a name="security-considerations-for-queries"></a>Consideraciones de seguridad para las consultas  

 Se deben tener en cuenta las consideraciones de seguridad siguientes cuando se consulta un modelo conceptual. Estas consideraciones se aplican a las consultas de [!INCLUDE[esql](../../../../../includes/esql-md.md)] que usan EntityClient y en las consultas de objetos que usan LINQ, los métodos del generador de consultas o [!INCLUDE[esql](../../../../../includes/esql-md.md)].  
  
#### <a name="prevent-sql-injection-attacks"></a>Impida los ataques de inyección de SQL.  

 A menudo, las aplicaciones obtienen entradas externas (de un usuario o de otro agente externo) y realizan acciones en función de dichas entradas. Cualquier entrada derivada directa o indirectamente del usuario o de un agente externo puede inyectar contenido que aproveche la sintaxis del lenguaje de destino para realizar acciones no autorizadas. Cuando el lenguaje de destino es un Lenguaje de consulta estructurado (SQL), como Transact-SQL, esta manipulación se conoce como ataque de inyección de SQL. Un usuario malintencionado puede inyectar comandos directamente en la consulta y colocar una tabla de la base de datos, provocar un ataque de denegación de servicio o cambiar de alguna otra forma la naturaleza de la operación que se está realizando.  
  
- Ataques de inyección de [!INCLUDE[esql](../../../../../includes/esql-md.md)]:  
  
     Los ataques de inyección de SQL se pueden realizar en [!INCLUDE[esql](../../../../../includes/esql-md.md)] proporcionando entradas malintencionadas a los valores que se utilizan en un predicado de consulta y en los nombres de los parámetros. Para evitar el riesgo de inyección de SQL, nunca debería combinar los datos proporcionados por el usuario con el texto de comandos de [!INCLUDE[esql](../../../../../includes/esql-md.md)].  
  
     Las consultas de [!INCLUDE[esql](../../../../../includes/esql-md.md)] aceptan parámetros siempre que se aceptan literales. Se deben usar consultas parametrizadas en lugar de insertar literales directamente en la consulta procedentes de un agente externo. También debe considerar el uso de [métodos del generador de consultas](/previous-versions/dotnet/netframework-4.0/bb896238(v=vs.100)) para construir Entity SQL de forma segura.  
  
- Ataques de inyección de LINQ to Entities:  
  
     Aunque la composición de consultas es posible en LINQ to Entities, se realiza a través de la API del modelo de objetos. A diferencia de [!INCLUDE[esql](../../../../../includes/esql-md.md)] las consultas, las consultas de LINQ to Entities no se componen mediante la manipulación o la concatenación de cadenas y no son susceptibles de ataques de inyección de SQL tradicionales.  
  
#### <a name="prevent-very-large-result-sets"></a>Evite los conjuntos de resultados muy grandes.  

 Un conjunto de resultados muy grande podría hacer que el sistema cliente se cerrara si el cliente realizara operaciones que consumieran recursos en proporción al tamaño del conjunto de resultados. Los conjuntos de resultados inesperadamente grandes se pueden producir en las condiciones siguientes:  
  
- En consultas con una base de datos grande que no incluyen las condiciones de filtro adecuadas.  
  
- En consultas que crean combinaciones cartesianas en el servidor.  
  
- En consultas de [!INCLUDE[esql](../../../../../includes/esql-md.md)].  
  
 Al aceptar datos proporcionados por el usuario, debe asegurarse de que no puedan provocar que los conjuntos de resultados se vuelvan mayores de lo que el sistema puede administrar. También puede utilizar el <xref:System.Linq.Queryable.Take%2A> método en LINQ to Entities o el operador [Limit](./language-reference/limit-entity-sql.md) en [!INCLUDE[esql](../../../../../includes/esql-md.md)] para limitar el tamaño del conjunto de resultados.  
  
#### <a name="avoid-returning-iqueryable-results-when-exposing-methods-to-potentially-untrusted-callers"></a>Evitar devolver resultados de IQueryable al exponer métodos a autores de llamadas que pueden no ser de confianza.  

 Evite devolver tipos <xref:System.Linq.IQueryable%601> desde métodos expuestos a autores de llamadas que pueden no ser de confianza por las siguientes razones:  
  
- Un consumidor de una consulta que expone un tipo <xref:System.Linq.IQueryable%601> podría llamar a métodos sobre el resultado que exponen datos seguros o aumenta el tamaño del conjunto de resultados. Por ejemplo, considere la siguiente firma de método:  

    ```csharp
    public IQueryable<Customer> GetCustomer(int customerId)
    ```

    Un consumidor de esta consulta podría llamar a `.Include("Orders")` sobre el `IQueryable<Customer>` devuelto para recuperar datos que la consulta no pretendía exponer. Esto se puede evitar cambiando el tipo de valor devuelto del método a <xref:System.Collections.Generic.IEnumerable%601> y llamando a un método (como `.ToList()`) que materialice los resultados.  
  
- Puesto que las consultas <xref:System.Linq.IQueryable%601> se ejecutan al iterar sobre los resultados, un consumidor de una consulta que expone un tipo <xref:System.Linq.IQueryable%601> podría interceptar las excepciones que se producen. Las excepciones podrían contener información no destinada para el consumidor.  
  
## <a name="security-considerations-for-entities"></a>Consideraciones de seguridad para entidades  

 Al generar y trabajar con tipos de entidad se aplican las consideraciones de seguridad siguientes.  
  
#### <a name="do-not-share-an-objectcontext-across-application-domains"></a>No comparta un ObjectContext a través de dominios de aplicación.  

 Al compartir un <xref:System.Data.Objects.ObjectContext> con más de un dominio de aplicación, se puede exponer información en la cadena de conexión. En su lugar, debería transferir objetos serializados o gráficos de objetos al otro dominio de aplicación y, a continuación, asociar esos objetos a <xref:System.Data.Objects.ObjectContext> en ese dominio de aplicación. Para obtener más información, vea [serializar objetos](/previous-versions/dotnet/netframework-4.0/bb738446(v=vs.100)).  
  
#### <a name="prevent-type-safety-violations"></a>Evite las infracciones de seguridad de los tipos.  

 Si se infringe la seguridad de tipos, el Entity Framework no puede garantizar la integridad de los datos de los objetos. Se podrían producir infracciones de seguridad de tipos si permite que las aplicaciones que no son de confianza se ejecuten con seguridad de acceso del código de plena confianza.  
  
#### <a name="handle-exceptions"></a>Controle las excepciones.  

 Obtenga acceso a los métodos y propiedades de un <xref:System.Data.Objects.ObjectContext> dentro de un bloque try-catch. La detección de excepciones evita que las excepciones no controladas expongan las entradas del <xref:System.Data.Objects.ObjectStateManager> o la información del modelo (tal como nombres de las tablas) a los usuarios de la aplicación.  
  
## <a name="security-considerations-for-aspnet-applications"></a>Consideraciones de seguridad para las aplicaciones ASP.NET  

Debe tener en cuenta lo siguiente al trabajar con rutas de acceso en aplicaciones de ASP.NET.  
  
#### <a name="verify-whether-your-host-performs-path-checks"></a>Compruebe si el host realiza comprobaciones de la ruta de acceso.  

 Cuando `|DataDirectory|` se usa la cadena de sustitución (entre barras verticales), ADO.net comprueba que se admite la ruta de acceso resuelta. Por ejemplo, ".." no se admite detrás de `DataDirectory`. La misma comprobación para resolver el operador raíz de la aplicación web ( `~` ) se realiza mediante el proceso que hospeda ASP.net. IIS realiza esta comprobación; sin embargo, los hosts que no sean IIS pueden no comprobar que la ruta de acceso resuelta se admite. Debe conocer el comportamiento del host en el que implementa una aplicación Entity Framework.  
  
#### <a name="do-not-make-assumptions-about-resolved-path-names"></a>No haga suposiciones sobre los nombres de ruta resueltos.  

 Aunque los valores a los que se resuelve el operador raíz ( `~` ) y la `DataDirectory` cadena de sustitución deben permanecer constantes durante el tiempo de ejecución de la aplicación, el Entity Framework no impide que el host modifique estos valores.  
  
#### <a name="verify-the-path-length-before-deployment"></a>Compruebe la longitud de la ruta de acceso antes de la implementación.  

 Antes de implementar una aplicación Entity Framework, debe asegurarse de que los valores del operador raíz (~) y la `DataDirectory` cadena de sustitución no superen los límites de la longitud de la ruta de acceso en el sistema operativo. Los proveedores de datos ADO.NET no garantizan que la longitud de la ruta de acceso esté dentro de los límites válidos.  
  
## <a name="security-considerations-for-adonet-metadata"></a>Consideraciones de seguridad de los metadatos de ADO.NET  

 Al generar y trabajar con los archivos de asignación y de modelo, se aplican las consideraciones de seguridad siguientes.  
  
#### <a name="do-not-expose-sensitive-information-through-logging"></a>No exponga información confidencial a través del registro.  

Los componentes del servicio de metadatos de ADO.NET no registran información privada. Si hay resultados que no se pueden devolver debido a las restricciones de acceso, los sistemas de administración de bases de datos y los sistemas de archivos no deberían devolver ningún resultado en lugar de generar una excepción que podría contener información confidencial.  
  
#### <a name="do-not-accept-metadataworkspace-objects-from-untrusted-sources"></a>No acepte objetos MetadataWorkspace de orígenes que no sean de confianza.  

 Las aplicaciones no deberían aceptar instancias de la clase <xref:System.Data.Metadata.Edm.MetadataWorkspace> de orígenes que no sean de confianza. En su lugar, debería construir y rellenar explícitamente un área de trabajo de este tipo de origen.  
  
## <a name="see-also"></a>Vea también

- [Proteger aplicaciones de ADO.NET](../securing-ado-net-applications.md)
- [Consideraciones de implementación](deployment-considerations.md)
- [Consideraciones sobre la migración](migration-considerations.md)
