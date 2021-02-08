---
description: 'Más información sobre: proveedor de reflexión (Servicios de datos de WCF)'
title: Proveedor de reflexión (Data Services de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: ef5ba300-6d7c-455e-a7bd-d0cc6d211ad4
ms.openlocfilehash: e09c9a86bb940681d8de24f5082919aea897795d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794928"
---
# <a name="reflection-provider-wcf-data-services"></a>Proveedor de reflexión (Data Services de WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Además de exponer los datos de un modelo de datos a través de la Entity Framework, Servicios de datos de WCF puede exponer datos que no estén definidos estrictamente en un modelo basado en entidad. El proveedor de reflexión expone los datos en clases que devuelven tipos que implementan la interfaz <xref:System.Linq.IQueryable%601>. Servicios de datos de WCF usa la reflexión para deducir un modelo de datos para estas clases y puede convertir las consultas basadas en direcciones en recursos en consultas basadas en Language Integrated Query (LINQ) en los <xref:System.Linq.IQueryable%601> tipos expuestos.

> [!NOTE]
> Puede utilizar el método <xref:System.Linq.Queryable.AsQueryable%2A> para devolver una interfaz de <xref:System.Linq.IQueryable%601> de cualquier clase que implemente la interfaz de <xref:System.Collections.Generic.IEnumerable%601>. Esto permite usar tipos de colección más genéricos como origen de datos para un servicio de datos.

El proveedor de reflexión admite las jerarquías de tipos. Para obtener más información, vea [Cómo: crear un servicio de datos mediante el proveedor de reflexión](create-a-data-service-using-rp-wcf-data-services.md).

## <a name="inferring-the-data-model"></a>Deducir el modelo de datos

Al crear el servicio de datos, el proveedor deduce el modelo de datos por medio de la reflexión. En la lista siguiente se muestra cómo el proveedor de reflexión deduce el modelo de datos:

- Contenedor de entidades: clase que expone los datos como propiedades que devuelven una instancia de <xref:System.Linq.IQueryable%601>. Al direccionar un modelo de datos basado en reflexión, el contenedor de entidades representa la raíz del servicio. Solo se admite una clase de contenedor de entidades para un espacio de nombres determinado.

- Conjuntos de entidades: las propiedades que devuelven instancias de <xref:System.Linq.IQueryable%601> se tratan como conjuntos de entidades. Los conjuntos de entidades se direccionan directamente como recursos en la consulta. Solo una propiedad del contenedor de entidades puede devolver una instancia de <xref:System.Linq.IQueryable%601> de un tipo determinado.

- Tipos de entidad: el tipo `T` del <xref:System.Linq.IQueryable%601> que devuelve el tipo de entidad. El proveedor de reflexión convierte las clases que forman parte de una jerarquía de herencia en una jerarquía de tipos de entidad equivalente.

- Claves de entidad: cada clase de datos que es un tipo de entidad debe tener una propiedad clave. Esta propiedad recibe el atributo <xref:System.Data.Services.Common.DataServiceKeyAttribute> (`[DataServiceKeyAttribute]`).

    > [!NOTE]
    > Solo debe aplicar el atributo <xref:System.Data.Services.Common.DataServiceKeyAttribute> a una propiedad que se pueda usar para identificar una instancia de forma única del tipo de entidad. Este atributo se ignora cuando se aplica a una propiedad de navegación.

- Propiedades de tipo de entidad: aparte de la clave de entidad, el proveedor de reflexión trata las propiedades accesibles no de indizador de una clase que no es un tipo de entidad como se explica a continuación:

  - Si la propiedad devuelve un tipo primitivo, se supone que es una propiedad de un tipo de entidad.

  - Si la propiedad devuelve un tipo que también es un tipo de entidad, se supone que es una propiedad de navegación que representa el extremo "uno" de una relación varios a uno o uno a uno.

  - Si la propiedad devuelve un <xref:System.Collections.Generic.IEnumerable%601> de un tipo de entidad, se supone que es una propiedad de navegación que representa el extremo "varios" de una relación uno a uno o varios a varios.

  - Si el tipo devuelto de la propiedad es un tipo de valor, la propiedad representa un tipo complejo.

> [!NOTE]
> A diferencia de un modelo de datos que está basado en el modelo de entidad-relación, los modelos que están basados en el proveedor de reflexión no entienden los datos relacionales. Debe utilizar el Entity Framework para exponer datos relacionales a través de Servicios de datos de WCF.

## <a name="data-type-mapping"></a>Asignación de tipos de datos

Cuando un modelo de datos se deduce de las clases de .NET Framework, los tipos primitivos del modelo se asignan a los tipos de datos de .NET Framework como sigue:

|Tipo de datos de .NET Framework|Tipo del modelo de datos|
|------------------------------|---------------------|
|<xref:System.Byte> `[]`|`Edm.Binary`|
|<xref:System.Boolean>|`Edm.Boolean`|
|<xref:System.Byte>|`Edm.Byte`|
|<xref:System.DateTime>|`Edm.DateTime`|
|<xref:System.Decimal>|`Edm.Decimal`|
|<xref:System.Double>|`Edm.Double`|
|<xref:System.Guid>|`Edm.Guid`|
|<xref:System.Int16>|`Edm.Int16`|
|<xref:System.Int32>|`Edm.Int32`|
|<xref:System.Int64>|`Edm.Int64`|
|<xref:System.SByte>|`Edm.SByte`|
|<xref:System.Single>|`Edm.Single`|
|<xref:System.String>|`Edm.String`|

> [!NOTE]
> Los tipos de valor NULL de .NET Framework se asignan a los mismo tipos del modelo de datos que los tipos de valor correspondientes a los que no se puede asignar un valor NULL.

## <a name="enabling-updates-in-the-data-model"></a>Habilitar las actualizaciones en el modelo de datos

Para permitir las actualizaciones de los datos que se exponen a través de este tipo de modelo de datos, el proveedor de reflexión define una interfaz <xref:System.Data.Services.IUpdatable>. Esta interfaz indica al servicio de datos cómo conservar las actualizaciones de los tipos expuestos. Para permitir las actualizaciones de los recursos que define el modelo de datos, la clase de contenedor de entidades debe implementar la interfaz de <xref:System.Data.Services.IUpdatable>. Para obtener un ejemplo de una implementación de la <xref:System.Data.Services.IUpdatable> interfaz, vea [Cómo: crear un servicio de datos mediante un origen de datos de LINQ to SQL](create-a-data-service-using-linq-to-sql-wcf.md).

La interfaz <xref:System.Data.Services.IUpdatable> necesita la implementación de los siguientes miembros para que las actualizaciones puedan propagarse al origen de datos por medio del proveedor de reflexión:

|Miembro|Descripción|
|------------|-----------------|
|<xref:System.Data.Services.IUpdatable.AddReferenceToCollection%2A>|Proporciona la funcionalidad para agregar un objeto a una colección de objetos relacionados a los que se tiene acceso desde una propiedad de navegación.|
|<xref:System.Data.Services.IUpdatable.ClearChanges%2A>|Proporciona la funcionalidad que cancela los cambios pendientes de los datos.|
|<xref:System.Data.Services.IUpdatable.CreateResource%2A>|Proporciona la funcionalidad para crear un recurso nuevo en el contenedor especificado.|
|<xref:System.Data.Services.IUpdatable.DeleteResource%2A>|Proporciona la funcionalidad para eliminar un recurso.|
|<xref:System.Data.Services.IUpdatable.GetResource%2A>|Proporciona la funcionalidad para recuperar un recurso que se identifica por una consulta y un nombre de tipo concretos.|
|<xref:System.Data.Services.IUpdatable.GetValue%2A>|Proporciona la funcionalidad para devolver el valor de una propiedad de un recurso.|
|<xref:System.Data.Services.IUpdatable.RemoveReferenceFromCollection%2A>|Proporciona la funcionalidad para quitar un objeto de una colección de objetos relacionados a los que se tiene acceso desde una propiedad de navegación.|
|<xref:System.Data.Services.IUpdatable.ResetResource%2A>|Proporciona la funcionalidad para actualizar un recurso especificado.|
|<xref:System.Data.Services.IUpdatable.ResolveResource%2A>|Proporciona la funcionalidad para devolver el recurso que se representa por una instancia de objeto concreta.|
|<xref:System.Data.Services.IUpdatable.SaveChanges%2A>|Proporciona la funcionalidad para guardar todos los cambios pendientes.|
|<xref:System.Data.Services.IUpdatable.SetReference%2A>|Proporciona la funcionalidad para establecer una referencia a objeto relacionada mediante una propiedad de navegación.|
|<xref:System.Data.Services.IUpdatable.SetValue%2A>|Proporciona la funcionalidad para establecer el valor de la propiedad de un recurso.|

## <a name="handling-concurrency"></a>Administrar la simultaneidad

Servicios de datos de WCF admite un modelo de simultaneidad optimista al permitirle definir un token de simultaneidad para una entidad. El servicio de datos utiliza este token de simultaneidad, que incluye una o más propiedades de la entidad, para determinar si se ha producido un cambio en los datos que se solicitan, que se están actualizando o eliminando. Cuando los valores de token obtenidos de la eTag de la solicitud difieren de los valores actuales de la entidad, el servicio de datos inicia una excepción. <xref:System.Data.Services.ETagAttribute> se aplica a un tipo de entidad para definir un token de simultaneidad en el proveedor de reflexión. El token de simultaneidad no puede incluir ninguna propiedad clave ni de navegación. Para obtener más información, vea [actualizar el servicio de datos](updating-the-data-service-wcf-data-services.md).

## <a name="using-linq-to-sql-with-the-reflection-provider"></a>Usar LINQ to SQL con el proveedor de reflexión

Dado que el Entity Framework se admite de forma nativa de forma predeterminada, es el proveedor de datos recomendado para usar datos relacionales con Servicios de datos de WCF. Sin embargo, puede utilizar el proveedor de reflexión para usar las clases LINQ to SQL con un servicio de datos. Los <xref:System.Data.Linq.Table%601> conjuntos de resultados devueltos por los métodos en el <xref:System.Data.Linq.DataContext> generado por el LINQ to SQL Object Relational Designer (Object Relational Designer) implementan la <xref:System.Linq.IQueryable%601> interfaz. Esto permite que el proveedor de reflexión tenga acceso a estos métodos y datos de entidades devueltos en SQL Server utilizando las clases LINQ to SQL generadas. Sin embargo, dado que LINQ to SQL no implementa la interfaz de <xref:System.Data.Services.IUpdatable>, necesita agregar una clase parcial que extiende la clase parcial existente <xref:System.Data.Linq.DataContext> para agregar la implementación <xref:System.Data.Services.IUpdatable>. Para obtener más información, vea [Cómo: crear un servicio de datos mediante un origen de datos de LINQ to SQL](create-a-data-service-using-linq-to-sql-wcf.md).

## <a name="see-also"></a>Vea también

- [Proveedores de Data Services](data-services-providers-wcf-data-services.md)
