---
title: Control de versiones del servicio
ms.date: 03/30/2017
ms.assetid: 37575ead-d820-4a67-8059-da11a2ab48e2
ms.openlocfilehash: fae0a5eca5737c3d7885cbe6c678678adabbea01
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245350"
---
# <a name="service-versioning"></a>Control de versiones del servicio

Después de la implementación inicial y de haber transcurrido potencialmente varias horas durante su duración, los servicios (y los puntos de conexión que exponen) pueden necesitar ser cambiados debido a diversas razones, como cambios en las necesidades comerciales, requisitos de tecnología de la información o para resolver otros problemas. Cada cambio produce una nueva versión del servicio. En este tema se explica cómo considerar el control de versiones en Windows Communication Foundation (WCF).  
  
## <a name="four-categories-of-service-changes"></a>Cuatro categorías de cambios del servicio  

 Los cambios en los servicios que se pueden requerir pueden clasificarse en cuatro categorías:  
  
- Cambios del contrato: por ejemplo, se podría agregar una operación o se podría agregar o cambiar un elemento de datos en un mensaje.  
  
- Cambios de la dirección: por ejemplo, se mueve un servicio a una ubicación diferente donde los puntos de conexión tienen nuevas direcciones.  
  
- Cambios del enlace: por ejemplo, un mecanismo de seguridad cambia o lo hace su configuración.  
  
- Cambios de implementación: por ejemplo, cuando cambia una implementación de método interno.  
  
 Algunos de estos cambios se denominan "con interrupción" y otros son denominados "sin interrupción". Un cambio es sin *interrupción* si todos los mensajes que se habrían procesado correctamente en la versión anterior se procesan correctamente en la nueva versión. Cualquier cambio que no cumpla ese criterio es un cambio *importante* .  
  
## <a name="service-orientation-and-versioning"></a>Orientación del servicio y control de las versiones  

 Uno de los principios de orientación del servicio es que los servicios y los clientes son autónomos (o independientes). Entre otras cosas, esto implica que los programadores del servicio no pueden suponer que controlan o que incluso lo saben todo sobre los clientes del servicio. Esto elimina la opción de recompilar y volver a implementar todos los clientes cuando un servicio cambia de versión. En este tema se supone que el servicio se adhiere a este principio de orientación y, por consiguiente, su modificación o el "control de versiones" tiene lugar con independencia de los clientes.  
  
 En los casos en los que no se prevé un cambio con interrupción y no puede evitarse, una aplicación puede decidir si omitir este principio y requerir que los clientes se recompilen y se implementen de nuevo con una nueva versión del servicio.  
  
## <a name="contract-versioning"></a>Versiones de contratos  

 Los contratos utilizados por un cliente no tienen por qué ser iguales que el contrato utilizado por el servicio; solo deben ser compatibles.  
  
 Para los contratos de servicios, la compatibilidad significa que se pueden agregar nuevas operaciones expuestas por el servicio pero que no se pueden quitar o cambiar semánticamente las operaciones existentes en el contrato.  
  
 Para los contratos de datos, la compatibilidad significa que se pueden agregar las nuevas definiciones de tipo de esquema pero las definiciones existentes de tipo de esquema no se pueden cambiar con interrupción. Los cambios con interrupción podrían incluir quitar los miembros de datos o cambiar de manera incompatible su tipo de datos. Esta característica da alguna libertad al servicio para cambiar la versión de sus contratos sin interrumpir a los clientes. En las dos secciones siguientes se explican los cambios no problemáticos e importantes que se pueden realizar en los contratos de servicio y datos de WCF.  
  
## <a name="data-contract-versioning"></a>Versiones de contratos de datos  

 Esta sección trata de datos que controlan las versiones al utilizar las clases <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.DataContractAttribute>.  
  
### <a name="strict-versioning"></a>Control estricto de las versiones  

 En muchos escenarios el cambio de versiones es un problema, el programador del servicio no tiene el control sobre los clientes y, por consiguiente, no puede suponer cómo reaccionarían a los cambios en el mensaje XML o esquema. En estos casos, debe garantizar que los nuevos mensajes se validarán ante el esquema anterior, por dos razones:  
  
- Los clientes anteriores se desarrollaron suponiendo que el esquema no cambiaría. No pueden procesar mensajes para los que nunca estuvieron diseñados.  
  
- Los clientes anteriores pueden realizar la validación del esquema real en el esquema anterior antes de intentar, incluso, procesar los mensajes.  
  
 El enfoque recomendado en tales escenarios es tratar los existentes contratos de datos como inmutables y crear nuevos contratos con nombres completos y únicos en XML. El programador del servicio agregaría a continuación los nuevos métodos a un contrato de servicios existente o crearía un nuevo contrato de servicios con métodos que utilizan el nuevo contrato de datos.  
  
 A menudo se dará el caso de que un programador del servicio necesite escribir alguna lógica empresarial que se debería ejecutar dentro de todas las versiones de un contrato de datos más el código empresarial específico para cada versión del contrato de datos. El apéndice que se encuentra al final de este tema explica cómo se pueden utilizar las interfaces para satisfacer esta necesidad.  
  
### <a name="lax-versioning"></a>Control de versiones lax  

 En muchos otros escenarios, el programador del servicio puede suponer que al agregar un nuevo miembro opcional al contrato de datos no se interrumpirán los clientes existentes. Esto exige al programador del servicio que investigue si los clientes existentes no realizan una validación del esquema y que si omiten a los miembros de datos desconocidos. En estos escenarios, es posible aprovecharse de las características del contrato de datos para agregar los nuevos miembros sin interrupción. El programador del servicio puede hacer esta suposición con confianza si las características del contrato de datos para controlar las versiones ya se utilizaron para la primera versión del servicio.  
  
 WCF, los servicios Web ASP.NET y muchas otras pilas de servicios web admiten el *control LAX de versiones*: es decir, no inician excepciones para los nuevos miembros de datos desconocidos en los datos recibidos.  
  
 Es fácil creer erróneamente que al agregar un nuevo miembro no se interrumpirán los clientes existentes. Si no está seguro de que todos los clientes puedan controlar el control lax de versiones, la recomendación es utilizar las instrucciones del control estricto de las versiones y tratar los contratos de datos como inmutables.  
  
 Para obtener instrucciones detalladas sobre el control de versiones de los contratos de datos LAX y estricta, vea [prácticas recomendadas: control de versiones de contratos de datos](best-practices-data-contract-versioning.md).  
  
### <a name="distinguishing-between-data-contract-and-net-types"></a>Distinguir entre los tipos de contrato de datos y .NET  

 Una clase o estructura .NET se puede proyectar como un contrato de datos aplicando el atributo <xref:System.Runtime.Serialization.DataContractAttribute> a la clase. El tipo .NET y sus proyecciones del contrato de datos son dos cuestiones distintas. Es posible tener varios tipos .NET con la misma proyección del contrato de datos. Esta distinción es especialmente útil para permitirle cambiar el tipo .NET mientras mantiene el contrato de datos proyectado, manteniendo así eso la compatibilidad con clientes existentes en el sentido estricto de la palabra. Hay dos cosas que siempre debería hacer para mantener esta distinción entre tipo .NET y contrato de datos:  
  
- Especifique <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> y <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A>. Siempre debería especificar el nombre y espacio de nombres de su contrato de datos para evitar que el nombre y espacio de nombres de su tipo .NET se expongan en el contrato. Así, si más tarde decide cambiar el espacio de nombres o nombre de tipo de .NET, el contrato de datos se mantiene invariable.  
  
- Especifique <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A>. Siempre debería especificar el nombre de sus miembros de datos para evitar que su nombre de miembro de .NET se exponga en el contrato. Esta manera, si más tarde decide cambiar el nombre de .NET del miembro, su contrato de datos seguirá siendo el mismo.  
  
### <a name="changing-or-removing-members"></a>Cambiar o quitar los miembros  

 Cambiar el nombre o el tipo de datos de un miembro, o quitar los miembros de datos se considera un cambio con interrupción, aun cuando se permite un control poco estricto de las versiones. Si es necesario, cree un nuevo contrato de datos.  
  
 Si la compatibilidad del servicio es de importancia elevada, podría considerar omitir los miembros de datos no usados en su código y dejarlos en su lugar. Si se divide un miembro de datos en varios miembros, se podría optar por dejar el miembro existente como una propiedad que pueda realizar la división necesaria y volver a agregar los clientes de nivel inferior (clientes que no se han actualizado a la última versión).  
  
 De igual forma, los cambios realizados al nombre del contrato de datos o al espacio de nombres son cambios con interrupción.  
  
### <a name="round-trips-of-unknown-data"></a>Ida y vuelta de datos desconocidos  

 En algunos escenarios, hay una necesidad de realizar una "ida y vuelta" de datos desconocidos que proceden de los miembros agregados en una nueva versión. Por ejemplo, un servicio de "versionNew" envía los datos con algunos miembros agregados recientemente a un cliente de "versionOld". El cliente omite los miembros recientemente agregados al procesar el mensaje, pero reenvía esos mismos datos, incluso los miembros agregados recientemente, de vuelta al servicio de versionNew. El escenario típico para esto son las actualizaciones de datos donde los datos se recuperan del servicio, se cambian y se devuelven.  
  
 Para habilitar el round-tripping para un tipo determinado, el tipo debe implementar la interfaz <xref:System.Runtime.Serialization.IExtensibleDataObject>. La interfaz contiene una propiedad, <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> que devuelve el tipo <xref:System.Runtime.Serialization.ExtensionDataObject>. La propiedad se utiliza para almacenar cualquier dato de las versiones futuras del contrato de datos que es desconocido para la versión actual. Estos datos son opacos para el cliente, pero cuando se serializa la instancia, el contenido de la propiedad <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> se escribe con el resto de los datos de los miembros del contrato de datos.  
  
 Se recomienda que todos sus tipos implementen esta interfaz para alojar los nuevos y desconocidos miembros futuros.  
  
### <a name="data-contract-libraries"></a>Bibliotecas de contratos de datos  

 Puede haber bibliotecas de contratos de datos donde un contrato se publica en un repositorio central y el servicio e implementadores de tipo implementan y exponen los contratos de datos de ese repositorio. En ese caso, al publicar un contrato de datos en el repositorio, no tiene ningún control sobre quién crea tipos que lo implementan. Por lo tanto, no puede modificar el contrato una vez publicado, por lo que se representa inmutable de manera efectiva.  
  
### <a name="when-using-the-xmlserializer"></a>Al utilizar XmlSerializer  

 Se aplican los mismos principios de control de versiones al utilizar la clase <xref:System.Xml.Serialization.XmlSerializer>. Cuando se requiere la versión estricta se requiere, trata los contratos de datos como inmutables y crea los nuevos contratos de datos con nombres únicos y completos para las nuevas versiones. Al estar seguro de que se puede utilizar el control lax para las versiones, puede agregar los nuevos miembros serializables en las nuevas versiones pero no puede cambiar o quitar los miembros existentes.  
  
> [!NOTE]
> <xref:System.Xml.Serialization.XmlSerializer> utiliza <xref:System.Xml.Serialization.XmlAnyElementAttribute> y los atributos <xref:System.Xml.Serialization.XmlAnyAttributeAttribute> para admitir viajes de ida y vuelta de los datos desconocidos.  
  
## <a name="message-contract-versioning"></a>Versiones de contratos de mensaje  

 Las instrucciones para las versiones de contrato de mensaje son muy similares al control de las versiones de los contratos de datos. Si se requiere el control estricto de las versiones, no debería cambiar el cuerpo de su mensaje pero, en su lugar, debería crear un nuevo contrato de mensaje con un nombre único y completo. Si sabe que puede utilizar el control lax de las versiones, puede agregar nuevas piezas del cuerpo del mensaje pero no puede cambiar o quitar las existentes. Esta orientación se aplica tanto a los contratos de mensaje sencillos como a los ajustados.  
  
 Se pueden agregar los encabezados del mensaje siempre, aun cuando el control estricto de versiones esté en uso. La marca MustUnderstand puede afectar a las versiones. En general, el modelo de control de versiones para los encabezados en WCF es como se describe en la especificación SOAP.  
  
## <a name="service-contract-versioning"></a>Control de las versiones del contrato de servicios  

 De manera parecida al control de las versiones del contrato de datos, el contrato de servicios que también controla las versiones implica agregar, cambiar y quitar operaciones.  
  
### <a name="specifying-name-namespace-and-action"></a>Especificar nombre, espacio de nombres y acción  

 De forma predeterminada, el nombre de un contrato de servicios es el nombre de la interfaz. Su espacio de nombres predeterminado es " http://tempuri.org ", y la acción de cada operación es " http://tempuri.org/contractname/methodname ". Se recomienda especificar explícitamente un nombre y espacio de nombres para el contrato de servicio y una acción para cada operación para evitar el uso de " http://tempuri.org " y evitar que los nombres de interfaz y método se expongan en el contrato del servicio.  
  
### <a name="adding-parameters-and-operations"></a>Agregar parámetros y operaciones  

 Agregar operaciones del servicio expuestas por el servicio es un cambio sin interrupción porque los clientes existentes no necesitan ocuparse de esas nuevas operaciones.  
  
> [!NOTE]
> Agregar las operaciones a un contrato de devolución de llamada dúplex es un cambio con interrupción.  
  
### <a name="changing-operation-parameter-or-return-types"></a>Cambiar el parámetro de operación o los tipos de valor devuelto  

 Cambiar el parámetro o los tipos de valor devuelto generalmente comportan un cambio con interrupción a menos que el nuevo tipo implemente el mismo contrato de datos implementado por el tipo anterior. Para realizar este cambio, agregue una nueva operación al contrato de servicios o defina un nuevo contrato de servicios.  
  
### <a name="removing-operations"></a>Quitar operaciones  

 Quitar las operaciones también es un cambio con interrupción. Para realizar este cambio, defina un nuevo contrato de servicios y expóngalo en un nuevo extremo.  
  
### <a name="fault-contracts"></a>Contrato de error  

 El atributo <xref:System.ServiceModel.FaultContractAttribute> permite que a un programador del contrato de servicios especifique la información sobre los errores que pueden devolver las operaciones del contrato.  
  
 La lista de errores descrita en el contrato de un servicio no se considera exhaustiva. En cualquier momento, una operación puede devolver errores que no se describen en su contrato. Cambiar, por consiguiente, el conjunto de errores descrito en el contrato no se considerado como con interrupción. Por ejemplo, agregar un nuevo error al contrato utilizando <xref:System.ServiceModel.FaultContractAttribute> o quitando un error existente del contrato.  
  
### <a name="service-contract-libraries"></a>Bibliotecas de contratos de servicios  

 Las organizaciones pueden tener bibliotecas de contratos donde un contrato se publica en un repositorio central y los implementadores de servicio y repositorio implementan los contratos desde ese repositorio. En este caso, al publicar un contrato de servicios en el repositorio, no tiene ningún control sobre quién crea servicios que lo implementan. Por tanto, no puede modificar el contrato de servicio una vez publicado, por lo que se presenta inmutable de manera efectiva. WCF admite la herencia de contratos, que se puede usar para crear un nuevo contrato que extienda los contratos existentes. Para utilizar esta característica, defina una nueva interfaz del contrato de servicios que se hereda de la interfaz del contrato de servicios anterior y, a continuación, agregue los métodos a la nueva interfaz. Cambia, a continuación, el servicio que implementa el contrato anterior para implementar el nuevo contrato y cambiar la definición de extremo de "versionOld" para utilizar el nuevo contrato. Para los clientes de "versionOld", el punto de conexión continuará apareciendo como si se expusiera el contrato de "versionOld"; para los clientes de "versionNew", el punto de conexión aparecerá para exponer el contrato de "versionNew."  
  
## <a name="address-and-binding-versioning"></a>Dirección y enlace de las versiones  

 Los cambios de la dirección del extremo y enlace son cambios con interrupción a menos que los clientes sean capaces de detectar dinámicamente la nueva dirección del extremo o enlace. Un mecanismo para implementar esta función consiste en utilizar un registro de la Descripción e integración de la detección universal (UDDI) y el patrón de invocación UDDI donde un cliente intenta comunicar con un punto de conexión y, en cuando se produce un error, consulta los metadatos del punto de conexión actual en un registro de UDDI conocido. El cliente utiliza a continuación la dirección y el enlace desde estos metadatos para comunicarse con el extremo. Si esta comunicación se realiza con éxito, el cliente almacena en caché la dirección e información de enlace para su uso en el futuro.  
  
## <a name="routing-service-and-versioning"></a>Servicio de enrutamiento y control de versiones  

 Si los cambios realizados en un servicio son cambios importantes y es necesario crear dos o más versiones diferentes de un servicio que se ejecuta simultáneamente, puede utilizar el servicio de enrutamiento de WCF para enrutar los mensajes a la instancia del servicio adecuada. El Servicio de enrutamiento de WCF usa enrutamiento basado en el contenido; es decir, usa información contenida en el mensaje para determinar dónde enrutarlo. Para obtener más información acerca del servicio de enrutamiento de WCF, vea [servicio de enrutamiento](./feature-details/routing-service.md). Para obtener un ejemplo de cómo usar el servicio de enrutamiento de WCF para el control de versiones del servicio, vea [Cómo: control de versiones del servicio](./feature-details/how-to-service-versioning.md).  
  
## <a name="appendix"></a>Apéndice  

 La recomendación general para el control de versiones de los contratos de datos es que cuando se necesite un control estricto de las versiones los contratos de datos se traten como inmutables y crear otros nuevos cuando se requieran cambios. Se necesita crear una nueva clase para cada nuevo contrato de datos, por lo que necesita que un mecanismo evite tener que tomar código existente, que se escribió referido a la clase del contrato de datos antiguo y volverlo a escribir, referido a la nueva clase del contrato de datos.  
  
 Dicho mecanismo se utiliza en interfaces para definir los miembros de cada contrato de datos y escribir el código de implementación interno, referido a las interfaces en lugar de referirse a las clases del contrato de datos que implementan las interfaces. El código siguiente para la versión 1 de un servicio muestra una interfaz `IPurchaseOrderV1` y `PurchaseOrderV1`:  
  
```csharp  
public interface IPurchaseOrderV1  
{  
    string OrderId { get; set; }  
    string CustomerId { get; set; }  
}  
  
[DataContract(  
Name = "PurchaseOrder",  
Namespace = "http://examples.microsoft.com/WCF/2005/10/PurchaseOrder")]  
public class PurchaseOrderV1 : IPurchaseOrderV1  
{  
    [DataMember(...)]  
    public string OrderId {...}  
    [DataMember(...)]  
    public string CustomerId {...}  
}  
```  
  
 Aunque las operaciones del contrato de servicios se escriban referidas a `PurchaseOrderV1`, la lógica empresarial real se referiría a `IPurchaseOrderV1`. En la versión 2 habría, como se muestra a continuación, una nueva interfaz `IPurchaseOrderV2` y una nueva clase `PurchaseOrderV2` en el código siguiente:  
  
```csharp
public interface IPurchaseOrderV2  
{  
    DateTime OrderDate { get; set; }  
}

[DataContract(
Name = "PurchaseOrder",  
Namespace = "http://examples.microsoft.com/WCF/2006/02/PurchaseOrder")]  
public class PurchaseOrderV2 : IPurchaseOrderV1, IPurchaseOrderV2  
{  
    [DataMember(...)]  
    public string OrderId {...}  
    [DataMember(...)]  
    public string CustomerId {...}  
    [DataMember(...)]  
    public DateTime OrderDate { ... }  
}  
```  
  
 El contrato de servicios se actualizaría para incluir las nuevas operaciones que se escriben referidas a `PurchaseOrderV2`. La lógica empresarial existente, escrita referida a `IPurchaseOrderV1` seguiría funcionando para `PurchaseOrderV2` y la nueva lógica empresarial que necesita la propiedad `OrderDate` se escribiría referida a `IPurchaseOrderV2`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A>
- <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A>
- <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>
- <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>
- <xref:System.Runtime.Serialization.IExtensibleDataObject>
- <xref:System.Runtime.Serialization.ExtensionDataObject>
- <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>
- <xref:System.Xml.Serialization.XmlSerializer>
- [Equivalencia del contrato de datos](./feature-details/data-contract-equivalence.md)
- [Devoluciones de llamadas en la serialización tolerante a versiones](./feature-details/version-tolerant-serialization-callbacks.md)
