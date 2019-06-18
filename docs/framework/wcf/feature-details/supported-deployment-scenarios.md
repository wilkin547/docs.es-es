---
title: 'Escenarios de implementación compatibles: WCF'
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: 2da55176cbfe618b332f2df210e3e1c0516b17ae
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2019
ms.locfileid: "67170050"
---
# <a name="supported-deployment-scenarios"></a>Escenarios de implementación admitidos

El subconjunto de las características de Windows Communication Foundation (WCF) que puede usar en aplicaciones de confianza parcial está diseñado para cumplir los requisitos de algunos, pero no todos, escenarios de uso de WCF. En el servidor, WCF cumple los requisitos de los proveedores de hospedaje compartidos que ejecutan aplicaciones de terceros en el permiso de confianza medio de ASP.NET 2.0 establecidos por razones de seguridad de la escala de Internet. En el cliente, la compatibilidad de confianza parcial de WCF está diseñado para cumplir los requisitos de tecnologías de implementación como [la implementación de ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) o tecnología de aplicación de explorador XAML de WPF, que permiten una implementación perfecta y segura de aplicaciones de escritorio de sitios de confianza.

## <a name="minimum-permission-requirements"></a>Requisitos mínimos de permiso

WCF admite un subconjunto de características de aplicaciones que se ejecutan bajo cualquiera de los siguientes conjuntos de permisos con nombre estándar:

- Permisos de nivel de confianza medio

- Permisos de zona de Internet

Intentó utilizar WCF en aplicaciones de confianza parcial con permisos más restrictivos puede producir excepciones de seguridad en tiempo de ejecución.

Para obtener más información sobre las características admitidas en estos conjuntos de permisos, consulte [Partial Trust Feature Compatibility](partial-trust-feature-compatibility.md).

## <a name="partial-trust-on-the-server"></a>Confianza parcial en el servidor

Muchos proveedores comerciales de la aplicación Web de ASP.NET que hospeda servicios exigen que ejecutan aplicaciones que se ejecutan en sus servidores en el conjunto de permisos de confianza medio de ASP.NET 2.0. Pueden ejecutar los servicios WCF en estos entornos suponiendo que usen el <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WebHttpBinding>, o el <xref:System.ServiceModel.WSHttpBinding> con seguridad de nivel de transporte.

Servicios WCF que se ejecutan en entornos de hospedaje de confianza medio también pueden actuar como servicios de nivel intermedio mediante el envío de mensajes a otros servidores en respuesta a las solicitudes de cliente. Se admiten los escenarios de nivel medio en el servidor si el entorno de hospedaje ha concedido a la aplicación el <xref:System.Net.WebPermission> adecuado para realizar solicitudes salientes al servidor deseado.

Además de mensajería SOAP mediante uno de los enlaces SOAP admitidos, WCF admite la <xref:System.ServiceModel.WebHttpBinding> para compilar servicios de estilo Web en aplicaciones de confianza parcial. El [modelo de programación de WCF Web HTTP](wcf-web-http-programming-model.md), [redifusión en WCF](wcf-syndication.md), y [integración de AJAX y compatibilidad de JSON](ajax-integration-and-json-support.md) todas las características de WCF son compatibles con confianza parcial.

Los servicios de flujo requieren permisos de plena confianza y no se pueden utilizar en aplicaciones de confianza parcial.

Para obtener más información, vea [Cómo: Uso de confianza media en ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=84603).

## <a name="partial-trust-on-the-client"></a>Confianza parcial en el cliente

Se deben tomar ciertas precauciones de seguridad al descargar y ejecutar código desde sitios de Internet que no sean de confianza. Ambos [la implementación de ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) y aprovechar la tecnología la aplicación de explorador de XAML de WPF (XBAP) uso de la confianza parcial para conceder permisos limitados (zona de Internet) al código no seguro.

Se puede usar WCF para comunicarse con servidores remotos desde dentro de aplicaciones de confianza parcial implementadas mediante [la implementación de ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) o XBAP. Incluye el conjunto de permisos de zona de Internet <xref:System.Net.WebPermission> para el host de origen, que permite a estas aplicaciones comunicarse con su servidor de origen mediante cualquiera de los enlaces WCF admitidos se describen en [Partial Trust Feature Compatibility ](partial-trust-feature-compatibility.md).

## <a name="see-also"></a>Vea también

- [Seguridad de acceso del código](../../misc/code-access-security.md)
- [Información general sobre aplicaciones hospedadas en Explorador de Windows Presentation Foundation](../../wpf/app-development/wpf-xaml-browser-applications-overview.md)
- [Confianza parcial](partial-trust.md)
- [Niveles de confianza de ASP.NET y los archivos de directivas](https://docs.microsoft.com/previous-versions/wyts434y(v=vs.140))
