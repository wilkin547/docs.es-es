---
title: Enlaces de Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], bindings
- Windows Communication Foundation [WCF], bindings
- bindings [WCF]
ms.assetid: 83639133-89f7-43f0-b4ef-8d9e57c08d25
ms.openlocfilehash: e69cd500c50e9d76824d0e438a1af86f3a722c52
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857693"
---
# <a name="windows-communication-foundation-bindings"></a>Enlaces de Windows Communication Foundation
Windows Communication Foundation (WCF) separa cómo se escribe el software para una aplicación de cómo se comunica con otro software. Los enlaces se usan para especificar el transporte, codificación y detalles protocolares requeridos para que los clientes y servicios se comuniquen entre sí. WCF usa los enlaces para generar la representación subyacente de conexión del punto de conexión, por lo que la mayoría de los detalles de enlace debe ser acordada por las partes que se están comunicando. La manera más sencilla de lograrlo es que los clientes de un servicio usen el mismo enlace que emplea el extremo para el servicio. Para obtener más información acerca de cómo hacerlo, consulte [uso de enlaces para configurar servicios y clientes](~/docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).  
  
 Un enlace se compone de una colección de elementos de enlace. Cada elemento describe algún aspecto de cómo el extremo se comunica con los clientes. Un enlace debe incluir por lo menos un elemento de enlace del transporte, por lo menos un elemento de enlace de la codificación de mensajes (que el elemento de enlace del transporte puede proporcionar de forma predeterminada), y cualquier número de otros elementos de enlace de protocolo. El proceso que compila un tiempo de ejecución a partir de esta descripción permite a cada elemento de enlace contribuir en el código a ese tiempo de ejecución.  
  
 WCF proporciona enlaces que contienen selecciones comunes de elementos de enlace. Éstos se pueden utilizar con su configuración predeterminada o puede modificar esos valores predeterminados según los requisitos del usuario. Estos enlaces proporcionados por el sistema tienen propiedades que permiten el control directo sobre los elementos de enlace y sus valores. También puede trabajar fácilmente y en paralelo con varias versiones de un enlace dando a cada versión del enlace un nombre propio. Para obtener más información, consulte [Configuring System-Provided enlaces](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md).  
  
 Si necesita una colección de elementos de enlace no proporcionada por uno de estos enlaces proporcionados por el sistema, puede crear un enlace personalizado que esté compuesto de la colección de elementos de enlace requeridos. Estos enlaces personalizados son fáciles de crear y no requieren una nueva clase, pero no proporcionan las propiedades para controlar los elementos de enlace o sus valores. Puede obtener acceso a los elementos de enlace y modificar sus valores a través de la colección que los contiene. Para obtener más información, consulte [enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Configuración de enlaces proporcionados por el sistema](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 Describe cómo utilizar y modificar los enlaces que proporciona WCF para admitir escenarios comunes.  
  
 [Utilización de enlaces para configurar servicios y clientes](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 Describe cómo definir los enlaces de Windows Communication Foundation (WCF) para servicios y clientes imperativamente en código y de manera declarativa mediante configuración.  
  
 [Enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md)  
 Describe qué es <xref:System.ServiceModel.Channels.CustomBinding> y cuándo se utiliza.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel.Channels.Binding>  
  
 <xref:System.ServiceModel.Channels.BindingElement>  
  
 <xref:System.ServiceModel.Channels.CustomBinding>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Extensión de enlaces](../../../../docs/framework/wcf/extending/extending-bindings.md)
