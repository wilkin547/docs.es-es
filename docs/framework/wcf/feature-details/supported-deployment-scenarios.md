---
title: Escenarios de implementación admitidos
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: a86fd9d50b2bdfa2daafa3bec98802d10a1efef5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43421078"
---
# <a name="supported-deployment-scenarios"></a>Escenarios de implementación admitidos
El subconjunto de las características de Windows Communication Foundation (WCF) que puede usar en aplicaciones de confianza parcial está diseñado para cumplir los requisitos de algunos, pero no todos, escenarios de uso de WCF. En el servidor, WCF cumple los requisitos de escala de Internet compartido los proveedores de hospedaje que ejecutan aplicaciones de terceros en el [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] conjunto por motivos de seguridad de permisos de nivel de confianza medio. En el cliente, la compatibilidad de confianza parcial de WCF está diseñado para cumplir los requisitos de tecnologías de implementación como [la implementación de ClickOnce](https://go.microsoft.com/fwlink/?LinkId=83712) o [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]de tecnología de aplicación de explorador XAML, lo que permite la conexión directa y segura implementación de aplicaciones de escritorio de sitios de confianza.  
  
## <a name="minimum-permission-requirements"></a>Requisitos mínimos de permiso  
 WCF admite un subconjunto de características de aplicaciones que se ejecutan bajo cualquiera de los siguientes conjuntos de permisos con nombre estándar:  
  
-   Permisos de nivel de confianza medio  
  
-   Permisos de zona de Internet  
  
 Intentó utilizar WCF en aplicaciones de confianza parcial con permisos más restrictivos puede producir excepciones de seguridad en tiempo de ejecución.  
  
 Para obtener más información sobre las características admitidas en estos conjuntos de permisos, consulte [Partial Trust Feature Compatibility](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## <a name="partial-trust-on-the-server"></a>Confianza parcial en el servidor  
 Muchos proveedores comerciales de servicios de hospedaje de aplicaciones web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] obligan a que las aplicaciones que se ejecutan en sus servidores se ejecuten en el conjunto de permisos Confianza media de [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] . Pueden ejecutar los servicios WCF en estos entornos suponiendo que usen el <xref:System.ServiceModel.BasicHttpBinding>, el <xref:System.ServiceModel.WebHttpBinding>, o el <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> con la seguridad de nivel de transporte.  
  
 Servicios WCF que se ejecutan en entornos de hospedaje de confianza medio también pueden actuar como servicios de nivel intermedio mediante el envío de mensajes a otros servidores en respuesta a las solicitudes de cliente. Se admiten los escenarios de nivel medio en el servidor si el entorno de hospedaje ha concedido a la aplicación el <xref:System.Net.WebPermission> adecuado para realizar solicitudes salientes al servidor deseado.  
  
 Además de mensajería SOAP mediante uno de los enlaces SOAP admitidos, WCF admite la <xref:System.ServiceModel.WebHttpBinding> para compilar servicios de estilo Web en aplicaciones de confianza parcial. El [modelo de programación de WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md), [redifusión en WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication.md), y [integración de AJAX y compatibilidad de JSON](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md) todas las características de WCF son compatibles con confianza parcial.  
  
 Los servicios de flujo requieren permisos de plena confianza y no se pueden utilizar en aplicaciones de confianza parcial.  
  
 Para obtener más información, consulte [Cómo: uso de confianza medio en ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=84603).  
  
## <a name="partial-trust-on-the-client"></a>Confianza parcial en el Cliente  
 Se deben tomar ciertas precauciones de seguridad al descargar y ejecutar código desde sitios de Internet que no sean de confianza. Ambos [la implementación de ClickOnce](https://go.microsoft.com/fwlink/?LinkId=83712) y [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]de la aplicación de explorador de XAML (XBAP) aprovechar la tecnología usar de confianza parcial para conceder permisos limitados (zona de Internet) al código no seguro.  
  
 Se puede usar WCF para comunicarse con servidores remotos desde dentro de aplicaciones de confianza parcial implementadas mediante [la implementación de ClickOnce](https://go.microsoft.com/fwlink/?LinkId=83712) o XBAP. Incluye el conjunto de permisos de zona de Internet <xref:System.Net.WebPermission> para el host de origen, que permite a estas aplicaciones comunicarse con su servidor de origen mediante cualquiera de los enlaces WCF admitidos se describen en [Partial Trust Feature Compatibility ](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## <a name="see-also"></a>Vea también  
 [Seguridad de acceso del código](https://go.microsoft.com/fwlink/?LinkId=83717)  
 [Información general sobre aplicaciones hospedadas en Explorador de Windows Presentation Foundation](https://go.microsoft.com/fwlink/?LinkId=98397)  
 [Confianza parcial](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 [Nivel de confianza medio de ASP.Net](https://go.microsoft.com/fwlink/?LinkId=69328)
