---
title: Creación de enlaces definidos por el usuario
ms.date: 03/30/2017
helpviewer_keywords:
- user-defined bindings [WCF]
ms.assetid: c4960675-d701-4bc9-b400-36a752fdd08b
ms.openlocfilehash: 34100569dc5cd5a340abca66fedca40ba21c1e0b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185645"
---
# <a name="creating-user-defined-bindings"></a>Creación de enlaces definidos por el usuario
Hay varias maneras de crear enlaces no proporcionadas por el sistema:  
  
- Cree un enlace personalizado, basado en la clase <xref:System.ServiceModel.Channels.CustomBinding>, que es un contenedor que rellena de elementos de enlace. El enlace personalizado se agrega a continuación a un punto de conexión de servicio. Puede crear el enlace personalizado mediante programación o mediante un archivo de configuración de la aplicación. Para usar un elemento de enlace desde un archivo de configuración de la aplicación, el elemento de enlace debe extenderse <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>. Para obtener más información acerca de los <xref:System.ServiceModel.Channels.CustomBinding>enlaces personalizados, vea [enlaces personalizados](custom-bindings.md) y .  
  
- Puede crear una clase que derive de un enlace estándar. Por ejemplo, puede derivar una clase de <xref:System.ServiceModel.WSHttpBinding> e invalidar el método <xref:System.ServiceModel.Channels.CustomBinding.CreateBindingElements%2A> para obtener los elementos de enlace e insertar un elemento de enlace personalizado o establecer un valor determinado de seguridad.  
  
- Puede crear un nuevo tipo <xref:System.ServiceModel.Channels.Binding> para controlar completamente toda la implementación del enlace.  
  
## <a name="the-order-of-binding-elements"></a>El orden de elementos de enlace  
 Cada elemento de enlace representa un paso del procesamiento al enviar y recibir mensajes. En tiempo de ejecución, los elementos de enlace crean los canales y agentes de escucha necesarios para crear pilas de canales entrantes y salientes.  
  
 Hay tres tipos principales de elementos de enlace: elementos de enlaces de protocolo, elementos de enlaces de codificación y elementos de enlaces de transporte.  
  
 Elementos de enlaces protocolares: estos elementos representan pasos de procesamiento de nivel superior que actúan sobre mensajes. Los canales y los agentes de escucha creados por estos elementos de enlace pueden agregar, quitar o modificar el contenido del mensaje. Un enlace determinado puede tener un número arbitrario de elementos de enlace de protocolo, cada uno de los cuales hereda de <xref:System.ServiceModel.Channels.BindingElement>. Windows Communication Foundation (WCF) incluye varios <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> elementos <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>de enlace de protocolo, incluidos el archivo .  
  
 Elemento de enlace de codificación: estos elementos representan las transformaciones entre un mensaje y una codificación lista para la transmisión en la conexión. Los enlaces WCF típicos incluyen exactamente un elemento de enlace de codificación. Entre los ejemplos de elementos de enlace de codificación se incluyen los elementos <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>, <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> y <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>. Si no se especifica un elemento de enlace de codificación para un enlace, se utiliza una codificación predeterminada. Cuando el transporte es HTTP, el valor predeterminado es texto, y, si no fuese HTTP, es binario.  
  
 Elemento de enlace de transporte: estos elementos representan la transmisión de un mensaje de codificación sobre un protocolo de transporte. Los enlaces WCF típicos incluyen exactamente un <xref:System.ServiceModel.Channels.TransportBindingElement>elemento de enlace de transporte, que hereda de . Entre los ejemplos de elementos de enlace del transporte se incluyen los elementos <xref:System.ServiceModel.Channels.TcpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpTransportBindingElement> y <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>.  
  
 Al crear nuevos enlaces, el orden de los elementos de enlace agregados es importante. Siempre agregue los elementos de enlace en el siguiente orden:  
  
|Nivel|Opciones|Obligatorio|  
|-----------|-------------|--------------|  
|Flujo de transacciones|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement?displayProperty=nameWithType>|Sin |  
|Confiabilidad|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement?displayProperty=nameWithType>|Sin |  
|Seguridad|<xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>|Sin |  
|Dúplex compuesto|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement?displayProperty=nameWithType>|Sin |  
|Encoding|Texto, binario, MTOM, personalizado|Sí\*|  
|Transporte|TCP, canalizaciones con nombre, HTTP, HTTPS, MSMQ, personalizado|Sí|  
  
\*Dado que se requiere una codificación para cada enlace, si no se especifica una codificación, WCF agrega una codificación predeterminada para usted. El valor predeterminado es texto/XML para los transportes HTTP y HTTPS, y binario para otros transportes.  
  
## <a name="creating-a-new-binding-element"></a>Creación de un nuevo elemento de enlace  
 Además de los <xref:System.ServiceModel.Channels.BindingElement> tipos derivados de los proporcionados por WCF, puede crear sus propios elementos de enlace. Esto le permite personalizar la manera en la que se crea la pila de enlaces y los componentes que van en ella creando su propio <xref:System.ServiceModel.Channels.BindingElement> que puede componerse con el resto de tipos proporcionados por el sistema en la pila.  
  
 Por ejemplo, si implementa un `LoggingBindingElement` que proporciona la capacidad de registrar el mensaje en una base de datos, debe colocarlo sobre un canal de transporte en la pila de canales. En este caso, la aplicación crea un enlace personalizado que compuso el `LoggingBindingElement` con `TcpTransportBindingElement`, como en el siguiente ejemplo.  
  
```csharp  
Binding customBinding = new CustomBinding(  
  new LoggingBindingElement(),
  new TcpTransportBindingElement()  
);  
```  
  
 La forma en la que escribe su nuevo elemento de enlace depende de su funcionalidad exacta. Uno de los ejemplos, [Transporte: UDP](../samples/transport-udp.md), proporciona una descripción detallada de cómo implementar un tipo de elemento de enlace.  
  
## <a name="creating-a-new-binding"></a>Crear un nuevo enlace  
 Un elemento de enlace creado por el usuario se puede utilizar de dos maneras. La sección anterior muestra la primera manera: a través de un enlace personalizado. Un enlace personalizado le permite al usuario crear su propio enlace en función de un conjunto arbitrario de elementos de enlace, incluso los creados por usuario.  
  
 Si utiliza el enlace en más de una aplicación, cree su propio enlace y extienda el <xref:System.ServiceModel.Channels.Binding>. Esto evita crear manualmente un enlace personalizado cada vez que desee utilizarlo. Un enlace definido por el usuario le permite definir el comportamiento del enlace e incluir elementos de enlace definidos por el usuario. Y está *pre-empaquetado*: no es necesario reconstruir el enlace cada vez que lo utilice.  
  
 Como mínimo, un enlace definido por el usuario deberá implementar el método <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> y la propiedad <xref:System.ServiceModel.Channels.Binding.Scheme%2A>.  
  
 El método <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> devuelve un nuevo <xref:System.ServiceModel.Channels.BindingElementCollection> que contiene los elementos de enlace del enlace. Se ordena la colección y debería contener primero los elementos de enlace protocolares, seguidos por el elemento de enlace de la codificación, seguido por el elemento de enlace de transporte. Al usar los elementos de enlace proporcionados por el sistema WCF, debe seguir las reglas de ordenación de elementos de enlace especificadas en [enlaces personalizados](custom-bindings.md). Esta colección nunca debería hacer referencia a objetos a los que se ha hecho referencia dentro de la clase de enlace definida por el usuario; por consiguiente, los autores de enlaces deben devolver un `Clone()` de la <xref:System.ServiceModel.Channels.BindingElementCollection> en cada llamada a <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A>.  
  
 La propiedad <xref:System.ServiceModel.Channels.Binding.Scheme%2A> representa el esquema del URI para el protocolo de transporte que se está utilizando en el enlace. Por ejemplo, *WSHttpBinding* y *NetTcpBinding* devuelven "http" y "net.tcp" de sus respectivas <xref:System.ServiceModel.Channels.Binding.Scheme%2A> propiedades.  
  
 Para obtener una lista completa de métodos y propiedades opcionales para los enlaces definidos por el usuario, vea <xref:System.ServiceModel.Channels.Binding>.  
  
### <a name="example"></a>Ejemplo  
 Este ejemplo implementa el enlace del perfil en `SampleProfileUdpBinding`, que deriva de <xref:System.ServiceModel.Channels.Binding>. Contiene `SampleProfileUdpBinding` hasta cuatro elementos de enlace dentro `UdpTransportBindingElement`de él: un usuario creado ; y tres proporcionados `TextMessageEncodingBindingElement` `CompositeDuplexBindingElement`por `ReliableSessionBindingElement`el sistema: , , y .  
  
```csharp
public override BindingElementCollection CreateBindingElements()  
{
    BindingElementCollection bindingElements = new BindingElementCollection();  
    if (ReliableSessionEnabled)  
    {  
        bindingElements.Add(session);  
        bindingElements.Add(compositeDuplex);  
    }  
    bindingElements.Add(encoding);  
    bindingElements.Add(transport);  
    return bindingElements.Clone();  
}  
```  
  
## <a name="security-restrictions-with-duplex-contracts"></a>Restricciones de Seguridad con contratos dúplex  
 No todos los elementos de enlace son compatibles entre sí. En concreto, hay algunas restricciones con respecto a elementos de enlaces de seguridad cuando se utilizan con contratos dúplex.  
  
### <a name="one-shot-security"></a>Seguridad monoestable  
 Puede implementar la seguridad "de un solo disparo", donde se envían todas `negotiateServiceCredential` las credenciales de seguridad necesarias en un solo mensaje, estableciendo el atributo del \<mensaje> elemento de configuración en `false`.  
  
 La autenticación monoestable no trabaja con contratos dúplex.  
  
 Para contratos de solicitud-respuesta, la autenticación monoestable solo funciona si la pila de enlaces bajo el elemento de enlace de seguridad admite la creación de instancias de <xref:System.ServiceModel.Channels.IRequestChannel> o <xref:System.ServiceModel.Channels.IRequestSessionChannel>.  
  
 Para contratos unidireccionales, la autenticación monoestable funciona si la pila de enlaces bajo el elemento de enlace de seguridad admite la creación de instancias de <xref:System.ServiceModel.Channels.IRequestChannel>, <xref:System.ServiceModel.Channels.IRequestSessionChannel>, <xref:System.ServiceModel.Channels.IOutputChannel> o <xref:System.ServiceModel.Channels.IOutputSessionChannel>.  
  
### <a name="cookie-mode-security-context-tokens"></a>Tokens de contexto de seguridad de modo de cookie  
 Los tokens de contexto de seguridad de modo de cookie no se pueden utilizar con contratos dúplex.  
  
 Para contratos de solicitud-respuesta, los tokens de contexto de seguridad del modo de cookie solo funcionan si la pila de enlaces bajo el elemento de enlace de seguridad admite la creación de instancias de <xref:System.ServiceModel.Channels.IRequestChannel> o <xref:System.ServiceModel.Channels.IRequestSessionChannel>.  
  
 Para contratos unidireccionales, los tokens de contexto de seguridad del modo de cookie funcionan si la pila de enlaces bajo el elemento de enlace de seguridad admite la creación de instancias de <xref:System.ServiceModel.Channels.IRequestChannel> o <xref:System.ServiceModel.Channels.IRequestSessionChannel>.  
  
### <a name="session-mode-security-context-tokens"></a>Tokens de contexto de seguridad de modo de sesión  
 El SCT de modo de sesión funciona con contratos dúplex si la pila de enlaces bajo el elemento de enlace de seguridad permite crear instancias de <xref:System.ServiceModel.Channels.IDuplexChannel> o <xref:System.ServiceModel.Channels.IDuplexSessionChannel>.  
  
 El SCT de modo de sesión funciona con contratos de solicitud-respuesta si la pila de enlaces bajo el elemento de enlace de seguridad permite crear instancias de <xref:System.ServiceModel.Channels.IDuplexChannel>, <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, <xref:System.ServiceModel.Channels.IRequestChannel> o <xref:System.ServiceModel.Channels.IRequestSessionChannel>.  
  
 El SCT de modo de sesión funciona con contratos unidireccionales si la pila de enlaces bajo el elemento de enlace de seguridad permite crear instancias de <xref:System.ServiceModel.Channels.IDuplexChannel>, <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, <xref:System.ServiceModel.Channels.IRequestChannel> o <xref:System.ServiceModel.Channels.IRequestSessionChannel>.  
  
## <a name="deriving-from-a-standard-binding"></a>Derivación a partir de un enlace estándar  
 En lugar de crear una clase de enlace completamente nueva, puede que sea posible extender uno de los enlaces existentes proporcionados por el sistema. De manera muy similar al caso anterior, debe invalidar el método <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> y la propiedad <xref:System.ServiceModel.Channels.Binding.Scheme%2A>.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Channels.Binding>
- [Enlaces personalizados](custom-bindings.md)
