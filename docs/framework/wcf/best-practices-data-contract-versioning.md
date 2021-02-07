---
description: 'Más información sobre: procedimientos recomendados: control de versiones de contratos de datos'
title: 'Procedimientos recomendados: Versiones de contratos de datos'
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- service contracts
- best practices [WCF], data contract versioning
- Windows Communication Foundation, data contracts
ms.assetid: bf0ab338-4d36-4e12-8002-8ebfdeb346cb
ms.openlocfilehash: 8f12c620b6916c7b513b3491cbbb91c4cfd1fbe5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686757"
---
# <a name="best-practices-data-contract-versioning"></a>Procedimientos recomendados: Versiones de contratos de datos

En este tema se enumeran los procedimientos recomendados para crear contratos de datos que pueden evolucionar con facilidad con el tiempo. Para obtener más información sobre los contratos de datos, vea los temas sobre el [uso de contratos de datos](./feature-details/using-data-contracts.md).  
  
## <a name="note-on-schema-validation"></a>Aviso en validación del esquema  

 En la explicación del control de versiones del contrato de datos, es importante tener en cuenta que el esquema del contrato de datos exportado por Windows Communication Foundation (WCF) no tiene ninguna compatibilidad con el control de versiones, aparte del hecho de que los elementos se marcan como opcionales de forma predeterminada.  
  
 Esto significa que no se puede implementar ni siquiera el escenario de versión más común, como agregar un nuevo miembro de datos, de un modo uniforme con respecto a un esquema determinado. Las versiones más recientes de un contrato de datos (con un nuevo miembro de datos, por ejemplo) no se validan mediante el esquema anterior.  
  
 Sin embargo, hay muchos escenarios en los cuales no se requiere compatibilidad de esquema estricta. Muchas plataformas de servicios Web, incluidos WCF y los servicios Web XML creados con ASP.NET, no realizan la validación de esquemas de forma predeterminada y, por tanto, toleran elementos adicionales que no se describen en el esquema. Cuando se trabaja con estas plataformas, muchos escenarios de versión son más fáciles de implementar.  
  
 De este modo, hay dos conjuntos de instrucciones de versión de contrato de datos: uno establecido para escenarios donde la validez estricta del esquema es importante, y otro conjunto para los escenarios cuando no lo es.  
  
## <a name="versioning-when-schema-validation-is-required"></a>Controlar versiones cuando se requiere la validación del esquema  

 Si se requiere la validez estricta del esquema en todas las direcciones (nuevo a anterior y anterior a nuevo), los contratos de datos se deberían considerar inmutables. Si es necesario controlar las versiones, se debería crear un nuevo contrato de datos, con un espacio de nombres o nombre diferente, y se deberían controlar las versiones del contrato de servicio utilizando el tipo de datos según corresponda.  
  
 Imagine, por ejemplo, que un contrato de servicio de procesamiento de pedidos de compra denominado `PoProcessing` con una operación `PostPurchaseOrder` toma un parámetro que se ajusta a un contrato de datos `PurchaseOrder`. Si el contrato `PurchaseOrder` tiene que cambiar, debe crear un nuevo contrato de datos, es decir, `PurchaseOrder2`, que incluya los cambios. A continuación, debe administrar la versión en el nivel del contrato de servicios. Por ejemplo, creando una operación `PostPurchaseOrder2` que toma el parámetro `PurchaseOrder2` o creando un contrato de servicios `PoProcessing2` donde la operación `PostPurchaseOrder` toma un contrato de datos `PurchaseOrder2`.  
  
 Tenga en cuenta que los cambios en los contratos de datos a los cuales hacen referencia otros contratos de datos también se extienden a la capa de modelo de servicio. Por ejemplo, en el escenario anterior, no es necesario cambiar el contrato de datos `PurchaseOrder`. Sin embargo, contiene un miembro de datos de un contrato de datos `Customer` que, a su vez, contiene un miembro de datos del contrato de datos `Address`, que debe cambiarse. En ese caso, necesitaría crear un contrato de datos `Address2` con los cambios necesarios, un contrato de datos `Customer2` que contenga el miembro de datos `Address2` y un contrato de datos `PurchaseOrder2` que contenga un miembro de datos `Customer2`. Como en el caso anterior, se tendrían que controlar las versiones del contrato de servicios también.  
  
 Aunque en estos nombres de ejemplos se cambian (anexando un "2"), la recomendación es cambiar los espacios de nombres en lugar de los nombres anexando los nuevos espacios de nombres con un número de versión o una fecha. Por ejemplo, el contrato de datos `http://schemas.contoso.com/2005/05/21/PurchaseOrder` cambiaría al contrato de datos `http://schemas.contoso.com/2005/10/14/PurchaseOrder`.  
  
 Para obtener más información, consulte procedimientos recomendados: [control de versiones del servicio](service-versioning.md).  
  
 En algunos casos, debe garantizar la compatibilidad estricta del esquema para los mensajes enviados por su aplicación, pero no puede confiar en que los mensajes entrantes sean estrictamente conformes al esquema. En este caso, existe el peligro de que un mensaje entrante pueda contener datos extraños. WCF almacena y devuelve los valores extraños, por lo que se envían mensajes no válidos para el esquema. Para evitar este problema, la característica de ida y vuelta debería estar desactivada. Existen dos formas de hacerlo.  
  
- No implemente la interfaz <xref:System.Runtime.Serialization.IExtensibleDataObject> en ninguno de sus tipos.  
  
- Aplique un atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> a su contrato de servicios con la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A> establecida en `true`.  
  
 Para obtener más información acerca de los recorridos de ida y vuelta, consulte [contratos de datos compatibles con el avance](./feature-details/forward-compatible-data-contracts.md).  
  
## <a name="versioning-when-schema-validation-is-not-required"></a>Controlar versiones cuando se requiere la validación del esquema  

 En raras ocasiones se requiere compatibilidad estricta de esquema. Muchas plataformas toleran elementos adicionales no descritos por un esquema. Siempre y cuando esto se tolere, se puede usar el conjunto completo de características que se describen en [contratos de datos con](./feature-details/forward-compatible-data-contracts.md) [versiones de contrato de datos](./feature-details/data-contract-versioning.md) y compatibles con reenvío. A continuación se indican algunas instrucciones recomendadas:  
  
 Algunas de las instrucciones se deben seguir con exactitud para enviar nuevas versiones de un tipo cuando se espera uno anterior o enviar uno anterior cuando se espera el nuevo. No se requieren otras instrucciones estrictamente, pero se enumeran aquí porque el futuro de versión del esquema puede afectar a.  
  
1. No intente controlar las versiones de los contratos de datos por herencia de tipo. Para crear versiones posteriores, cambie el contrato de datos en un tipo existente o cree un nuevo tipo no relacionado.  
  
2. Se permite el uso de herencia junto con los contratos de datos, siempre que la herencia no se utilice como un mecanismo de control de versiones y se sigan ciertas reglas. Si un tipo deriva de un cierto tipo base, no le haga derivar de un tipo base diferente en una versión futura (a menos que tenga el mismo contrato de datos). Existe una excepción: puede insertar un tipo en la jerarquía entre un tipo de contrato de datos y su tipo base, pero solo si no contiene miembros de datos con los mismos nombres en calidad de otros miembros en ninguna versión posible de los otros tipos de la jerarquía. En general, el uso de miembros de datos con los mismos nombres en niveles diferentes de la misma jerarquía de herencia puede producir problemas de versión serios y se debería evitar.  
  
3. Iniciándose con la primera versión de un contrato de datos, siempre implemente <xref:System.Runtime.Serialization.IExtensibleDataObject> para habilitar alrededor tropezando. Para obtener más información, vea [Forward-Compatible Data Contracts](./feature-details/forward-compatible-data-contracts.md) (Contratos de datos compatibles con el reenvío). Si ha soltado una o más versiones de un tipo sin implementar esta interfaz, impleméntela en la versión siguiente del tipo.  
  
4. En versiones posteriores, no cambie el nombre de contrato de datos o espacio de nombres. Si cambia el nombre o espacio de nombres del tipo subyacente al contrato de datos, asegúrese de conservar el nombre de contrato de datos y espacio de nombres utilizando los mecanismos adecuados, como la propiedad <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> de <xref:System.Runtime.Serialization.DataContractAttribute>. Para obtener más información acerca de la nomenclatura, consulte [nombres de contratos de datos](./feature-details/data-contract-names.md).  
  
5. En versiones posteriores, no cambie los nombres de ningún miembro de datos. Si cambia el nombre del campo, propiedad o evento subyacente al miembro de datos, utilice la propiedad `Name` de <xref:System.Runtime.Serialization.DataMemberAttribute> para conservar el nombre del miembro de datos existente.  
  
6. En versiones posteriores, no cambie el tipo de ningún campo, propiedad o evento subyacente al miembro de datos de tal manera que el contrato de datos resultante para ese miembro de datos cambie. Tenga presente que los tipos de interfaz son equivalentes a <xref:System.Object> con el fin de determinar el contrato de datos esperado.  
  
7. En versiones posteriores, no cambie el orden de los miembros de datos existentes mediante el ajuste de la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> del atributo <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
8. En versiones posteriores, se pueden agregar nuevos miembros de datos. Deberían seguir siempre estas reglas:  
  
    1. La propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> se debería dejar siempre en su valor predeterminado de `false`.  
  
    2. Si el miembro no acepta el valor predeterminado `null` o cero, se debería proporcionar un método de devolución de llamada mediante <xref:System.Runtime.Serialization.OnDeserializingAttribute> para proporcionar un valor predeterminado razonable en caso de que el miembro no se encuentre en la secuencia de entrada. Para obtener más información sobre la devolución de llamada, consulte [devoluciones de llamada de serialización tolerante a versiones](./feature-details/version-tolerant-serialization-callbacks.md).  
  
    3. La <xref:System.Runtime.Serialization.DataMemberAttribute.Order?displayProperty=nameWithType> propiedad se debe usar para asegurarse de que todos los miembros de datos recién agregados aparecen después de los miembros de datos existentes. Para hacerlo, se recomienda lo siguiente: Ninguno de los miembros de datos en la primera versión del contrato de datos debería tener su propiedad `Order` establecida. Todos los miembros de datos agregados en la versión 2 del contrato de datos deberían tener su propiedad `Order` establecida en 2. Todos los miembros de datos agregados en la versión 3 del contrato de datos deberían tener su propiedad `Order` establecida en 3, etc. Se permite tener más de un miembro de datos establecido en el mismo número de `Order`.  
  
9. No quite los miembros de datos en versiones posteriores, ni siquiera si la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> se dejó en su propiedad predeterminada de `false` en versiones anteriores.  
  
10. No cambie la propiedad `IsRequired` en ningún miembro de datos existente entre versiones.  
  
11. Para los miembros de datos necesarios (donde `IsRequired` es `true`), no cambie la propiedad `EmitDefaultValue` entre versiones.  
  
12. No intente crear jerarquías de versión bifurcadas. Es decir, siempre debería haber una ruta de acceso en al menos una dirección desde una versión a otra versión utilizando solo los cambios permitidos por estas instrucciones.  
  
     Por ejemplo, si la versión 1 de un contrato de datos Persona contiene solo el Nombre de miembro de datos, no debería crear la versión 2a de la adición del contrato añadiendo solo el miembro Edad y la versión 2 agregando solo el miembro Dirección. Al ir de 2a a 2b, implicaría quitar Edad y agregar Dirección; al ir en la otra dirección, supondría quitar Dirección y agregar Edad. Estas instrucciones no permiten quitar los miembros.  
  
13. Generalmente no debería crear nuevos subtipos de tipos de contrato de datos existente en una nueva versión de su aplicación. Por la misma razón, no debería crear nuevos contratos de datos que se usen en lugar de miembros de datos declarados como Object o como tipos de interfaz. Se permite crear estas clases nuevas solo cuando conoce que puede agregar los nuevos tipos a la lista de tipos conocida de todas las instancias de su aplicación anterior. Por ejemplo, en la versión 1 de su aplicación, puede tener el tipo de contrato de datos LibraryItem con Book y subtipos de contrato de datos Newspaper. LibraryItem entonces tendría una lista de tipos que contendría Book y Newspaper. Suponga que ahora agrega un tipo Magazine en la versión 2 qué es un subtipo de LibraryItem. Si envía una instancia Magazine de la versión 2 a la versión 1, el contrato de datos Magazine no se encuentra en la lista de tipos conocidos y se inicia una excepción.  
  
14. No debería agregar o quitar los miembros de enumeración entre las versiones. Tampoco debería cambiar el nombre de los miembros de la enumeración, a menos que use la propiedad Name en el atributo `EnumMemberAttribute` para mantener iguales sus nombres en el modelo del contrato de datos.  
  
15. Las colecciones son intercambiables en el modelo del contrato de datos, tal y como se describe en [tipos de colección en contratos de datos](./feature-details/collection-types-in-data-contracts.md). Esto permite un gran grado de flexibilidad. Sin embargo, asegúrese de que no cambia inadvertidamente un tipo de colección de una manera no intercambiable entre versiones. Por ejemplo, no cambie de una colección no personalizada (es decir, sin el atributo `CollectionDataContractAttribute` ) a una personalizada o una colección personalizada a una no personalizada. Tampoco cambie las propiedades de `CollectionDataContractAttribute` entre las versiones. El único cambio permitido es agregar una propiedad Name o Namespace si el nombre del tipo de colección subyacente o el espacio de nombres ha cambiado y necesita cambiar su nombre de contrato de datos y espacio de nombres al mismo nombre que en una versión anterior.  
  
 Se pueden omitir algunas de las instrucciones enumeradas aquí sin ningún riesgo cuando se aplican circunstancias especiales. Asegúrese de que entiende totalmente la serialización, deserialización y mecanismos de esquema implicados en caso de no cumplir las instrucciones.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>
- <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>
- <xref:System.Runtime.Serialization.IExtensibleDataObject>
- <xref:System.ServiceModel.ServiceBehaviorAttribute>
- <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>
- <xref:System.Runtime.Serialization.ExtensionDataObject>
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>
- [Utilización de contratos de datos](./feature-details/using-data-contracts.md)
- [Versiones de contratos de datos](./feature-details/data-contract-versioning.md)
- [Nombres de contratos de datos](./feature-details/data-contract-names.md)
- [Contratos de datos compatibles con el reenvío](./feature-details/forward-compatible-data-contracts.md)
- [Devoluciones de llamadas en la serialización tolerante a versiones](./feature-details/version-tolerant-serialization-callbacks.md)
