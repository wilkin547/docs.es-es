---
title: Escenarios de implementación admitidos
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: 6898ec33564a526d0e444502ebb6ed7f142f1856
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347978"
---
# <a name="supported-deployment-scenarios"></a>Escenarios de implementación admitidos

El subconjunto de características de Windows Communication Foundation (WCF) que se pueden usar en aplicaciones de confianza parcial está diseñado para cumplir los requisitos de algunos escenarios, pero no todos, para usar WCF. En el servidor, WCF cumple los requisitos de los proveedores de hospedaje compartido de escala de Internet que ejecutan aplicaciones de terceros en el conjunto de permisos ASP.NET 2,0 Medium Trust establecido por motivos de seguridad. En el cliente, la compatibilidad de confianza parcial de WCF se ha diseñado para cumplir los requisitos de tecnologías de implementación como [ClickOnce Deployment](/visualstudio/deployment/clickonce-security-and-deployment) o la tecnología de aplicación de explorador XAML de WPF, que permiten una implementación perfecta y segura de aplicaciones de escritorio desde sitios que no son de confianza.

## <a name="minimum-permission-requirements"></a>Requisitos mínimos de permisos

WCF admite un subconjunto de características en aplicaciones que se ejecutan en cualquiera de los siguientes conjuntos de permisos con nombre estándar:

- Permisos de nivel de confianza medio

- Permisos de zona de Internet

Si se intenta usar WCF en aplicaciones de confianza parcial con permisos más restrictivos, pueden producirse excepciones de seguridad en tiempo de ejecución.

Para obtener más información sobre las características admitidas en estos conjuntos de permisos, consulte [Partial Trust Feature Compatibility](partial-trust-feature-compatibility.md).

## <a name="partial-trust-on-the-server"></a>Confianza parcial en el servidor

Muchos proveedores comerciales de servicios de hospedaje de aplicaciones Web de ASP.NET exigen que las aplicaciones que se ejecutan en sus servidores se ejecuten en el conjunto de permisos ASP.NET 2,0 Medium Trust. Los servicios WCF se pueden ejecutar en estos entornos siempre que usen el <xref:System.ServiceModel.BasicHttpBinding>, el <xref:System.ServiceModel.WebHttpBinding>o el <xref:System.ServiceModel.WSHttpBinding> con seguridad de nivel de transporte.

Los servicios WCF que se ejecutan en entornos de hospedaje de confianza medio también pueden actuar como servicios de nivel intermedio enviando mensajes a otros servidores en respuesta a solicitudes de clientes. Se admiten los escenarios de nivel medio en el servidor si el entorno de hospedaje ha concedido a la aplicación el <xref:System.Net.WebPermission> adecuado para realizar solicitudes salientes al servidor deseado.

Además de la mensajería SOAP que usa uno de los enlaces SOAP admitidos, WCF admite el <xref:System.ServiceModel.WebHttpBinding> para la creación de servicios de estilo Web en aplicaciones de confianza parcial. El [modelo de programación web http de WCF](wcf-web-http-programming-model.md), la [sindicación de WCF](wcf-syndication.md)y la integración de Ajax y las características de [compatibilidad con JSON](ajax-integration-and-json-support.md) de WCF se admiten en confianza parcial.

Los servicios de flujo requieren permisos de plena confianza y no se pueden utilizar en aplicaciones de confianza parcial.

Para obtener más información, consulte [Cómo: usar la confianza media en ASP.NET 2,0](https://go.microsoft.com/fwlink/?LinkId=84603).

## <a name="partial-trust-on-the-client"></a>Confianza parcial en el cliente

Se deben tomar ciertas precauciones de seguridad al descargar y ejecutar código desde sitios de Internet que no sean de confianza. Tanto la [implementación de ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) como la tecnología de aplicación de explorador XAML (XBAP) de WPF hacen uso de la confianza parcial para conceder permisos limitados (zona de Internet) a código que no es de confianza.

WCF se puede usar para comunicarse con servidores remotos desde aplicaciones de confianza parcial implementadas mediante [ClickOnce Deployment](/visualstudio/deployment/clickonce-security-and-deployment) o XBAP. El conjunto de permisos de la zona de Internet incluye <xref:System.Net.WebPermission> para el host de origen, que permite a estas aplicaciones comunicarse con su servidor de origen mediante cualquiera de los enlaces de WCF admitidos descritos en [compatibilidad de características de confianza parcial](partial-trust-feature-compatibility.md).

## <a name="see-also"></a>Vea también

- [Seguridad de acceso del código](../../misc/code-access-security.md)
- [Información general sobre las aplicaciones hospedadas en el Explorador Windows Presentation Foundation](../../wpf/app-development/wpf-xaml-browser-applications-overview.md)
- [Confianza parcial](partial-trust.md)
- [Niveles de confianza y archivos de directiva de ASP.NET](https://docs.microsoft.com/previous-versions/wyts434y(v=vs.140))
