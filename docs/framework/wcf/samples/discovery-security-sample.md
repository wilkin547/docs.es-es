---
title: Ejemplo de seguridad de la detección
ms.date: 03/30/2017
ms.assetid: b8db01f4-b4a1-43fe-8e31-26d4e9304a65
ms.openlocfilehash: 00f81d1879d9157a7ecdfa0db8d2ea0d505ad5b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183741"
---
# <a name="discovery-security-sample"></a>Ejemplo de seguridad de la detección

La especificación de la detección no requiere que los puntos de conexión que participan en el proceso de detección sean seguros. Al mejorar los mensajes de detección gracias a la seguridad, se mitigan varios tipos de ataques (alteración del mensaje, denegación de servicio, repetición y suplantación). Este ejemplo implementa canales personalizados que calculan y comprueban las firmas de mensaje utilizando el formato de firma compacto (descrito en la sección 8.2 de la especificación de detección WS). El ejemplo admite la [especificación de detección de 2005](http://specs.xmlsoap.org/ws/2005/04/discovery/ws-discovery.pdf) y la [versión 1.1.](http://docs.oasis-open.org/ws-dd/discovery/1.1/cs-01/wsdd-discovery-1.1-spec-cs-01.pdf)  
  
 El canal personalizado se aplica encima de la pila del canal existente para los puntos de conexión de anuncio y detección. De esta manera, se aplica un encabezado de firma para cada mensaje enviado. La firma se comprueba en los mensajes recibidos, y cuando no coincide o cuando los mensajes no tienen una firma, los mensajes se quitan. Para firmar y comprobar los mensajes, el ejemplo utiliza los certificados.  
  
## <a name="discussion"></a>Discusión  
 WCF es muy extensible y permite a los usuarios la posibilidad de personalizar los canales según deseen. En el ejemplo se implementa un elemento de enlace seguro de detección que crea canales seguros. Los canales seguros aplican y comprueban las firmas de los mensajes, y se aplican encima de la pila actual.  
  
 El elemento de enlace seguro crea generadores de canales seguros y agentes de escucha del canal.  
  
## <a name="secure-channel-factory"></a>Generador de canales seguro  
 El generador de canales seguro crea canales dúplex o de salida que agregan una firma compacta a los encabezados de mensaje. Para mantener el tamaño de los mensajes lo más pequeño posible, se utiliza el formato de firma compacta. La estructura de una firma compacta se muestra en el siguiente ejemplo.  
  
```xml  
<d:Security ... >
  [<d:Sig Scheme="xs:anyURI"
         [KeyId="xs:base64Binary"]?  
          Refs="..."  
         [PrefixList]="xs:NMTOKENS"
          Sig="xs:base64Binary"
          ... />]?  
  ...
</d:Security>  
```  
  
> [!NOTE]
> `PrefixList` se agregó en el protocolo de la versión de detección de 2008.  
  
 Para calcular la firma, el ejemplo determina los elementos de firma expandidos. Se crea una firma XML (`SignedInfo`), utilizando el prefijo del espacio de nombres `ds`, tal y como requiere la especificación de la detección WS. En la firma se hace referencia al cuerpo y a todos los encabezados en los espacios de nombres de direccionamiento y detección, de modo que no se puedan alterar. Cada elemento al que se hacehttp://www.w3.org/2001/10/xml-exc-c14n# referencia se transforma mediante la Canonicalización exclusivahttp://www.w3.org/2000/09/xmldsig#sha1 ( ) y, a continuación, se calcula un valor de resumen SHA-1 ( ). En función de todos los elementos a los que sehttp://www.w3.org/2000/09/xmldsig#rsa-sha1 hace referencia y sus valores de resumen, el valor de firma se calcula mediante el algoritmo RSA ( ).  
  
 Los mensajes se firman con un certificado especificado por el cliente. Cuando se crea el elemento de enlace, se debe especificar la ubicación del almacén, el nombre y el nombre de asunto del certificado. El `KeyId` de la firma compacta representa el identificador de clave del token de firma y es el identificador de clave de asunto (SKI) del token de firma o (si el SKI no existe) un valor hash SHA-1 de la clave pública del token de firma.  
  
## <a name="secure-channel-listener"></a>Agente de escucha del canal seguro  
 El agente de escucha del canal seguro crea canales dúplex o de entrada que comprueban la firma compacta en los mensajes recibidos. Para comprobar la firma, el `KeyId` especificado en la firma compacta adjuntada al mensaje se utiliza para seleccionar un certificado del almacén especificado. Si el mensaje no tiene ninguna firma o su comprobación no es correcta, los mensajes se quitan. Para utilizar el enlace seguro, el ejemplo define un generador que crea objetos <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> y <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> personalizados con el elemento de enlace seguro de detección agregado. Estos extremos seguros se pueden utilizar en agentes de escucha de anuncio de detección y en los servicios que pueden detectarse.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 En el ejemplo se incluyen una biblioteca y cuatro aplicaciones de consola:  
  
- **DiscoverySecurityChannels**: biblioteca que expone el enlace seguro. La biblioteca calcula y comprueba la firma compacta para los mensajes entrantes o salientes.  
  
- **Servicio:** un servicio que expone el contrato ICalculatorService, autohospedado. El servicio se marca como detectable. El usuario especifica los detalles del certificado utilizados para firmar los mensajes especificando la ubicación del almacén y nombre, y el nombre de asunto u otro identificador único para el certificado, y el almacén donde se encuentran los certificados de cliente (que se usan para comprobar la firma de los mensajes entrantes). Según estos detalles, se compila y se usa un UdpDiscoveryEndpoint.  
  
- **Cliente:** esta clase intenta detectar un ICalculatorService y llamar a métodos en el servicio. De nuevo, se crea un <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> con seguridad agregada y se usa para firmar y comprobar los mensajes.  
  
- **AnnouncementListener**: Un servicio autohospedado que escucha anuncios en línea y sin conexión y utiliza el punto de conexión de anuncio seguro.  
  
> [!NOTE]
> Si Setup.bat se ejecuta varias veces, el administrador de certificados le solicita que elija un certificado que agregar, ya que hay certificados duplicados. En ese caso, Setup.bat se debería anular y se debería llamar a Cleanup.bat, porque los duplicados ya se han creado. Cleanup.bat también le solicita que elija un certificado que eliminar. Seleccione un certificado en la lista y siga ejecutando Cleanup.bat hasta que no quede ningún certificado.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1. Ejecute el script Setup.bat desde un símbolo del sistema para desarrolladores para Visual Studio. El ejemplo usa los certificados para firmar y comprobar los mensajes. El script crea los certificados mediante Makecert.exe y, a continuación, los instala utilizando Certmgr.exe. El script se debe ejecutar con privilegios de administrador.  
  
2. Para compilar y ejecutar el ejemplo, abra el archivo Security.sln en Visual Studio y elija **Reconstruir todo**. Actualizar las propiedades de la solución para iniciar varios proyectos: seleccione **Inicio** para todos los proyectos excepto DiscoverySecureChannels. Ejecute la solución normalmente.  
  
3. Una vez haya terminado con el ejemplo, ejecute el script Cleanup.bat que quita los certificados creados para este ejemplo.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DiscoveryScenario`  
