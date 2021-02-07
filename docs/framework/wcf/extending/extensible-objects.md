---
description: 'Más información sobre: objetos extensibles'
title: Objetos extensibles
ms.date: 03/30/2017
helpviewer_keywords:
- extensible objects [WCF]
ms.assetid: bc88cefc-31fb-428e-9447-6d20a7d452af
ms.openlocfilehash: 80082f4c94adf2d668ff4c241d286959d9a05038
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756700"
---
# <a name="extensible-objects"></a>Objetos extensibles

El patrón de objeto extensible se utiliza para extender clases de tiempo de ejecución existentes con nueva funcionalidad o para agregar un nuevo estado a un objeto. Las extensiones, asociadas a uno de los objetos extensibles, permiten que los comportamientos en fases muy diferentes de procesamiento tengan acceso al estado compartido y funcionalidad adjuntos a un objeto extensible común al que pueden tener acceso.

## <a name="the-iextensibleobjectt-pattern"></a>El \<T> patrón IExtensibleObject

Hay tres interfaces en el patrón de objeto extensible: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>y <xref:System.ServiceModel.IExtensionCollection%601>.

Los tipos que permiten a los objetos <xref:System.ServiceModel.IExtensibleObject%601> personalizar su funcionalidad implementan la interfaz <xref:System.ServiceModel.IExtension%601>.

Los objetos extensibles permiten la agregación dinámica de objetos <xref:System.ServiceModel.IExtension%601>. Los objetos <xref:System.ServiceModel.IExtension%601> son caracterizados por la interfaz siguiente:

```csharp
public interface IExtension<T>
where T : IExtensibleObject<T>
{
    void Attach(T owner);
    void Detach(T owner);
}
```

La restricción de tipo garantiza que las extensiones solo se pueden definir para las clases que son <xref:System.ServiceModel.IExtensibleObject%601>. <xref:System.ServiceModel.IExtension%601.Attach%2A> y <xref:System.ServiceModel.IExtension%601.Detach%2A> proporcionan notificación de agregación o desagregación.

Es válido para que las implementaciones restrinjan cuando se pueden agregar y quitar de un propietario. Por ejemplo, puede impedir la eliminación por completo, impedir agregar o eliminar extensiones cuando el propietario o extensión están en un cierto estado, impedir agregar a varios propietarios simultáneamente o permitir solo una suma única seguida por una sola eliminación.

<xref:System.ServiceModel.IExtension%601> no implica ninguna interacción con otras interfaces administradas estándar. En concreto, el método <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> en el objeto de propietario no desasocia normalmente sus extensiones.

Cuando se agrega una extensión a la colección, se llama a <xref:System.ServiceModel.IExtension%601.Attach%2A> antes de que entre en la colección. Cuando se quita una extensión de la colección, se llama <xref:System.ServiceModel.IExtension%601.Detach%2A> después de quitarla. Esto significa (suponiendo que la sincronización sea correcta) que una excepción solo se puede encontrar en la colección mientras está entre <xref:System.ServiceModel.IExtension%601.Attach%2A> y <xref:System.ServiceModel.IExtension%601.Detach%2A>.

El objeto pasado a <xref:System.ServiceModel.IExtensionCollection%601.FindAll%2A> o <xref:System.ServiceModel.IExtensionCollection%601.Find%2A> no necesita ser <xref:System.ServiceModel.IExtension%601> (por ejemplo, puede pasar cualquier objeto), pero la extensión que se devuelve es <xref:System.ServiceModel.IExtension%601>.

Si ninguna extensión de la colección es <xref:System.ServiceModel.IExtension%601> , <xref:System.ServiceModel.IExtensionCollection%601.Find%2A> devuelve NULL y <xref:System.ServiceModel.IExtensionCollection%601.FindAll%2A> devuelve una colección vacía. Si varias extensiones implementan <xref:System.ServiceModel.IExtension%601>, <xref:System.ServiceModel.IExtensionCollection%601.Find%2A> devuelve una de ellas. El valor devuelto de <xref:System.ServiceModel.IExtensionCollection%601.FindAll%2A> es una captura.

Hay dos escenarios principales. El primer escenario utiliza la propiedad <xref:System.ServiceModel.IExtensibleObject%601.Extensions%2A> como un diccionario basado en tipos para insertar el estado en un objeto y permitir, de este modo, que otro componente lo pueda examinar utilizando el tipo.

El segundo escenario utiliza <xref:System.ServiceModel.IExtension%601.Attach%2A> y las propiedades <xref:System.ServiceModel.IExtension%601.Detach%2A> para permitir que un objeto participe en el comportamiento personalizado, como registrarse para los eventos, inspeccionar las transiciones de estado, etc.

La interfaz <xref:System.ServiceModel.IExtensionCollection%601> es una colección de objetos <xref:System.ServiceModel.IExtension%601> que permiten recuperar <xref:System.ServiceModel.IExtension%601> por su tipo. <xref:System.ServiceModel.IExtensionCollection%601.Find%2A?displayProperty=nameWithType> devuelve el objeto agregado más recientemente que es una <xref:System.ServiceModel.IExtension%601> de ese tipo.

### <a name="extensible-objects-in-windows-communication-foundation"></a>Objetos extensibles en Windows Communication Foundation

Hay cuatro objetos extensibles en Windows Communication Foundation (WCF):

- <xref:System.ServiceModel.ServiceHostBase>. Ésta es la clase base para el host del servicio.  Las extensiones de esta clase se pueden utilizar para extender el comportamiento del <xref:System.ServiceModel.ServiceHostBase> o almacenar el estado para cada servicio.

- <xref:System.ServiceModel.InstanceContext>. Esta clase conecta una instancia del tipo de servicio con el servicio en tiempo de ejecución.  Contiene información sobre la instancia así como una referencia al <xref:System.ServiceModel.InstanceContext> que contiene <xref:System.ServiceModel.ServiceHostBase>. Las extensiones de esta clase se pueden utilizar para extender el comportamiento del <xref:System.ServiceModel.InstanceContext> o almacenar el estado para cada servicio.

- <xref:System.ServiceModel.OperationContext>. Esta clase representa la información de la operación que el tiempo de ejecución reúne para cada operación.  Esto incluye información como los encabezados de los mensajes entrantes, las propiedades de los mensajes entrantes, la identidad de seguridad de entrada y otra información.  Las extensiones de esta clase pueden extender el comportamiento de <xref:System.ServiceModel.OperationContext> o almacenar el estado para cada operación.

- <xref:System.ServiceModel.IContextChannel> : Esta interfaz permite inspeccionar cada estado de los canales y los proxies generados por el tiempo de ejecución de WCF.  Las extensiones de esta clase pueden extender el comportamiento de <xref:System.ServiceModel.IClientChannel> o utilizarlo para almacenar el estado de cada canal.

En el ejemplo de código siguiente se puede ver el uso de una extensión simple para seguir la pista de los objetos <xref:System.ServiceModel.InstanceContext>.

[!code-csharp[IInstanceContextInitializer#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/iinstancecontextinitializer/cs/initializer.cs#1)]

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.IExtensibleObject%601>
- <xref:System.ServiceModel.IExtension%601>
- <xref:System.ServiceModel.IExtensionCollection%601>
