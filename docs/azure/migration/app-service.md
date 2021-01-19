---
title: Migración de una aplicación web o un servicio de .NET a Azure App Service
description: Aprenda aspectos relacionados con la migración de un servicio o una aplicación web .NET de un entorno local a Azure App Service.
ms.topic: conceptual
ms.date: 07/08/2020
ms.openlocfilehash: 0e2aaa23aedabef007878901ec7297711f140533
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189257"
---
# <a name="migrate-your-net-web-app-or-service-to-azure-app-service"></a>Migración de una aplicación web o un servicio de .NET a Azure App Service

[App Service](/azure/app-service/overview) es una plataforma de procesos completamente administrada y optimizada para el hospedaje de sitios y aplicaciones web escalables. En este artículo se proporciona información acerca de cómo realizar una migración mediante lift-and-shift de una aplicación existente al Azure App Service, las modificaciones que hay que tener en cuenta y los recursos adicionales para [trasladarse a la nube](https://azure.microsoft.com/migration/web-applications/). La mayoría de servicios (API web y WCF) y sitios web de ASP.NET (Webforms y MVC) pueden moverse directamente a Azure App Service sin realizar ningún cambio. Algunos pueden necesitar cambios menores, mientras que otros pueden necesitar cierta refactorización.

¿Listo para comenzar? [Publique su una aplicación ASP.NET + SQL en Azure App Service](https://tutorials.visualstudio.com/azure-webapp-migrate/intro).

## <a name="considerations"></a>Consideraciones

### <a name="on-premises-resources-including-sql-server"></a>Recursos locales (incluido SQL Server)

Compruebe el acceso a los recursos locales, ya que es posible que haya que migrarlos o cambiarlos. Estas son las opciones para mitigar el acceso a los recursos locales:

* Crear una VPN que conecte App Service a recursos locales mediante [Azure Virtual Networks](/azure/app-service/web-sites-integrate-with-vnet).
* Exponer de forma segura servicios locales en la nube sin cambios en el firewall mediante [Azure Relay](/azure/service-bus-relay/relay-what-is-it).
* Migrar dependencias como un [base de datos SQL](./sql.md) a Azure.
* Usar las ofertas de plataforma como servicio en la nube para reducir las dependencias. Por ejemplo, en lugar de conectarse a un servidor de correo local, considere la posibilidad de usar [SendGrid](/azure/sendgrid-dotnet-how-to-send-email).

### <a name="port-bindings"></a>Enlaces de puerto

Azure App Service admite el puerto 80 para el tráfico HTTP y el puerto 443 para el tráfico HTTPS.

En el caso de WCF, se admite los siguientes enlaces:

| Enlaces | Notas |
|--|--|
| `BasicHttp` |  |
| `WSHttp` |  |
| `WSDualHttpBinding` | La [compatibilidad con socket web](/azure/app-service/web-sites-configure) debe habilitarse. | La [compatibilidad con socket web](/azure/app-service/web-sites-configure) debe habilitarse. |
| `NetHttpBinding` | La [compatibilidad con socket web](/azure/app-service/web-sites-configure) debe habilitarse en los contratos dúplex. | La [compatibilidad con socket web](/azure/app-service/web-sites-configure) debe habilitarse en los contratos dúplex. |
| `NetHttpsBinding` | La [compatibilidad con socket web](/azure/app-service/web-sites-configure) debe habilitarse en los contratos dúplex. | La [compatibilidad con socket web](/azure/app-service/web-sites-configure) debe habilitarse en los contratos dúplex. |
| `BasicHttpContextBinding` |  |
| `WebHttpBinding` |  |
| `WSHttpContextBinding` |  |

### <a name="authentication"></a>Autenticación

Azure App Service admite la autenticación anónima de forma predeterminada y la autenticación mediante formularios cuando se plantea. La autenticación de Windows solo se puede usar mediante la integración con Azure Active Directory y ADFS. [Obtenga más información acerca de cómo integrar sus directorios locales con Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).

### <a name="assemblies-in-the-gac-global-assembly-cache"></a>Ensamblados en la GAC (caché global de ensamblados)

No es una opción admitida. Considere la posibilidad de copiar los ensamblados necesarios en la carpeta *\bin* de la aplicación. No se pueden usar los archivos *.msi* personalizados instalados en el servidor (por ejemplo, los generadores de PDF).

### <a name="iis-settings"></a>Configuración de IIS

Todo lo que tradicionalmente se configuraba mediante applicationHost.config en la aplicación, ahora se puede configurar mediante Azure Portal. Esto se aplica al valor de bits de AppPool, la opción para habilitar y deshabilitar WebSockets, la versión de canalización administrada, la versión de .NET Framework (2.0 o 4.0), etc. Para modificar la [configuración de la aplicación](/azure/app-service/web-sites-configure), vaya a [Azure Portal](https://portal.azure.com), abra la hoja de la aplicación web y, a continuación, seleccione la pestaña **Configuración de la aplicación**.

#### <a name="iis5-compatibility-mode"></a>Modo de compatibilidad con IIS5

El modo de compatibilidad con IIS5 no se admite. En Azure App Service, cada aplicación web y todas sus aplicaciones dependientes se ejecutan en el mismo proceso de trabajo con un conjunto específico de [grupos de aplicaciones](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc735247(v=ws.10)).

#### <a name="iis7-schema-compliance"></a>Cumplimiento del esquema de IIS7 +

Algunos elementos y atributos no se definen en el esquema de IIS de Azure App Service. Si tiene problemas, considere la posibilidad de usar [transformaciones XDT](/azure/app-service/configure-common).

#### <a name="single-application-pool-per-site"></a>Un único grupo de aplicaciones por sitio

En Azure App Service, cada aplicación web y todas las aplicaciones dependientes se ejecutan en el mismo grupo de aplicaciones. Considere la posibilidad de establecer un único grupo de aplicaciones con una configuración común, o bien crear una aplicación web independiente para cada aplicación.

### <a name="com-and-com-components"></a>Componentes COM y COM+

Azure App Service no permite el registro de componentes COM en la plataforma. Si una aplicación usa cualquiera de los componentes COM, estos deben reescribirse en código administrado e implementarse en el sitio o la aplicación.

### <a name="physical-directories"></a>Directorios físicos

Azure App Service no permite el acceso a la unidad física. Para acceder a los archivos a través de SMB, es posible que deba usar [Azure Files](/azure/storage/files/storage-files-introduction). [Azure Blob Storage](/azure/storage/blobs/storage-blobs-introduction) puede almacenar archivos para el acceso a través de HTTPS.

### <a name="isapi-filters"></a>Filtros ISAPI

Azure App Service puede admitir el uso de los filtros ISAPI; sin embargo, la DLL de ISAPI se debe implementar en el sitio y registrar a través de web.config.

### <a name="https-bindings-and-ssl"></a>Enlaces HTTPS y SSL

Los enlaces HTTPS no se migrarán ni tampoco lo harán los certificados SSL asociados con los sitios web. Sin embargo, [los certificados SSL se pueden cargar manualmente](/azure/app-service/app-service-web-tutorial-custom-ssl) una vez que se completa la migración del sitio.

### <a name="sharepoint-and-frontpage"></a>SharePoint y FrontPage

Las extensiones de servidor de FrontPage y de SharePoint (FPSE) no se admiten.

### <a name="web-site-size"></a>Tamaño del sitio web

Los sitios gratuitos tienen un límite de 1 GB de contenido. Si el suyo tiene más de 1 GB, debe actualizarlo a una SKU de pago. Consulte [Precios de App Service](https://azure.microsoft.com/pricing/details/app-service/windows/).

### <a name="database-size"></a>Tamaño de base de datos

En el caso de las bases de datos de SQL Server, consulte los actuales [precios de SQL Database](https://azure.microsoft.com/pricing/details/sql-database).

### <a name="azure-active-directory-aad-integration"></a>Integración de Azure Active Directory (AAD)

AAD no funciona con aplicaciones gratuitas. Para usar AAD, debe actualizar la SKU de la aplicación. Consulte [Precios de App Service](https://azure.microsoft.com/pricing/details/app-service/windows/).

### <a name="monitoring-and-diagnostics"></a>Supervisión y diagnóstico

Es poco probable que sus soluciones locales de supervisión y diagnóstico funcionen en la nube. Sin embargo, Azure proporciona herramientas de registro, supervisión y diagnóstico para que pueda identificar y depurar los problemas con las aplicaciones web. Puede habilitar fácilmente el diagnóstico de la aplicación web en su configuración, y puede ver los registros guardados por Azure Application Insights. [Obtenga más información acerca de cómo habilitar el registro de diagnósticos para las aplicaciones web](/azure/app-service/web-sites-enable-diagnostic-log).

### <a name="connection-strings-and-application-settings"></a>Configuración de la aplicación y cadenas de conexión

Considere la posibilidad de usar [Azure KeyVault](/azure/key-vault/), un servicio que almacena de forma segura la información confidencial que se usa en la aplicación. También puede almacenar estos datos como un valor de configuración de App Service.

### <a name="dns"></a>DNS

Puede que tenga que actualizar las opciones de configuración de DNS según los requisitos de la aplicación. Las opciones de DNS pueden configurarse en la [configuración de dominio personalizado](/azure/app-service/app-service-web-tutorial-custom-domain), en App Service.

## <a name="azure-app-service-with-windows-containers"></a>Azure App Service con contenedores de Windows

Si la aplicación no se puede migrar directamente a App Service, considere la posibilidad de que App Service use contenedores de Windows, lo que permite usar la GAC, los componentes COM, archivos MSI, acceso completo a las API de .NET FX, DirectX, etc.

## <a name="see-also"></a>Vea también

* [Cómo determinar si la aplicación cumple los requisitos para App Service](https://appmigration.microsoft.com/)
* [Traslado de la base de datos a la nube](sql.md)
* [Restricciones y detalles del espacio aislado de aplicaciones web de Azure](https://github.com/projectkudu/kudu/wiki/Azure-Web-App-sandbox)
