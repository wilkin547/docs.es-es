---
description: 'Más información acerca de: materialización de objetos (Servicios de datos de WCF)'
title: Materialización de objetos (Servicios de datos de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, querying
ms.assetid: f0dbf7b0-0292-4e31-9ae4-b98288336dc1
ms.openlocfilehash: 4beb72b9fb4402ee9a751b870f012bfa2cf15951
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794980"
---
# <a name="object-materialization-wcf-data-services"></a>Materialización de objetos (Servicios de datos de WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Cuando se usa el cuadro de diálogo **Agregar referencia de servicio** para consumir una fuente de Open Data Protocol (OData) en una aplicación cliente basada en .NET Framework, se generan clases de datos equivalentes para cada tipo de entidad del modelo de datos expuesto por la fuente. Para obtener más información, vea [generar la biblioteca de cliente del servicio de datos](generating-the-data-service-client-library-wcf-data-services.md). Los datos de entidad devueltos por una consulta se materializan en una instancia de una de estas clases de servicio de datos de cliente generadas. Para obtener información sobre las opciones de combinación y la resolución de identidad para los objetos sometidos a seguimiento, vea [administrar el contexto del servicio de datos](managing-the-data-service-context-wcf-data-services.md).

Servicios de datos de WCF también le permite definir sus propias clases de servicio de datos de cliente en lugar de usar las clases de datos generadas por la herramienta. De esta forma, puede usar sus propias clases de datos, que también se conocen como clases de datos "tipos de objetos CLR antiguos sin formato" (POCO). Al utilizar estos tipos de clases de datos personalizadas, debe atribuir la clase de datos con <xref:System.Data.Services.Common.DataServiceKeyAttribute> o <xref:System.Data.Services.Common.DataServiceEntityAttribute> y asegurarse de que los nombres de tipo en el cliente coincidan con los nombres de tipo en el modelo de datos del servicio de datos.

Una vez que la Biblioteca recibe el mensaje de respuesta de la consulta, materializa los datos devueltos de la fuente de OData en instancias de las clases del servicio de datos del cliente que son del tipo de la consulta. El proceso general para materializar estos objetos es el siguiente:

1. La biblioteca de cliente lee el tipo serializado desde el elemento `entry` en la fuente del mensaje de respuesta e intenta crear una nueva instancia del tipo correcto de una de estas formas:

    - Cuando el tipo declarado en la fuente tenga el mismo nombre que el tipo de la clase <xref:System.Data.Services.Client.DataServiceQuery%601>, se crea una nueva instancia de este tipo mediante el constructor vacío.

    - Cuando el tipo declarado en la fuente tenga el mismo tipo que se deriva del tipo de la clase <xref:System.Data.Services.Client.DataServiceQuery%601>, se crea una nueva instancia de este tipo derivado mediante el constructor vacío.

    - Cuando el tipo declarado en la fuente no se pueda hacer coincidir con el tipo de la clase <xref:System.Data.Services.Client.DataServiceQuery%601> ni con ningún tipo derivado, se crea una nueva instancia del tipo consultado mediante el constructor vacío.

    - Cuando se establezca la propiedad <xref:System.Data.Services.Client.DataServiceContext.ResolveType%2A>, se llama al delegado proporcionado para invalidar la asignación de tipos basada en nombre predeterminada y, en su lugar, se crea una nueva instancia del tipo devuelto por el delgado <xref:System.Func%602>. Si este delegado devuelve un valor NULL, en su lugar se crea una nueva instancia del tipo consultado. Quizá sea necesario invalidar la asignación de nombre basada en tipo predeterminada para admitir escenarios de herencia.

2. La biblioteca de cliente lee el valor de URI desde el elemento `id` de `entry`, que es el valor de identidad de la entidad. A menos que se use un valor de la propiedad <xref:System.Data.Services.Client.DataServiceContext.MergeOption%2A> de la enumeración <xref:System.Data.Services.Client.MergeOption.NoTracking>, se usa el valor de identidad para realizar el seguimiento del objeto en la clase <xref:System.Data.Services.Client.DataServiceContext>. El valor de identidad también se usa para garantizar que solo se cree una única instancia de identidad, aunque se devuelva varias veces una entidad en la respuesta de la consulta.

3. La biblioteca de cliente lee propiedades desde la entrada de la fuente y establece las propiedades correspondientes en el objeto recién creado. Cuando un objeto con el mismo valor de identidad se produce en la clase <xref:System.Data.Services.Client.DataServiceContext>, las propiedades se establecen basándose en la configuración de <xref:System.Data.Services.Client.MergeOption> de la clase <xref:System.Data.Services.Client.DataServiceContext>. Puede que la respuesta contenga valores de propiedad para los que no se produzca ninguna propiedad correspondiente en el tipo de cliente. En este caso, la acción depende del valor de la propiedad <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> de la clase <xref:System.Data.Services.Client.DataServiceContext>. Cuando esta propiedad se establece en `true`, se ignora la propiedad que falta. En caso contrario, se produce un error. Las propiedades se establecen de la siguiente forma:

    - Las propiedades escalares se establecen en el valor correspondiente de la entrada del mensaje de respuesta.

    - Las propiedades complejas se establecen en una nueva instancia de tipo complejo, que se establecen con las propiedades del tipo complejo de la respuesta.

    - Las propiedades de navegación que devuelven una colección de entidades relacionadas se establecen en una instancia nueva o en una instancia existente de la interfaz <xref:System.Collections.Generic.ICollection%601>, donde `T` es el tipo de entidad relacionada. Esta colección está vacía a menos que se hayan cargado los objetos relacionados en la clase <xref:System.Data.Services.Client.DataServiceContext>. Para obtener más información, vea [cargar contenido diferido](loading-deferred-content-wcf-data-services.md).

      > [!NOTE]
      > Cuando las clases de datos del cliente generadas admitan el enlace de datos, las propiedades de navegación devuelven instancias de la clase <xref:System.Data.Services.Client.DataServiceCollection%601> en su lugar. Para obtener más información, consulte [enlazar datos a controles](binding-data-to-controls-wcf-data-services.md).

4. Se genera el evento <xref:System.Data.Services.Client.DataServiceContext.ReadingEntity>.

5. La biblioteca de clientes adjunta el objeto a la clase <xref:System.Data.Services.Client.DataServiceContext>. El objeto no se adjunta cuando la clase <xref:System.Data.Services.Client.MergeOption> es la enumeración <xref:System.Data.Services.Client.MergeOption.NoTracking>.

## <a name="see-also"></a>Vea también

- [Consultar el servicio de datos](querying-the-data-service-wcf-data-services.md)
- [Proyecciones de consultas](query-projections-wcf-data-services.md)
