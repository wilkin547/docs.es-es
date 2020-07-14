---
title: Seguridad y serialización
description: Lea acerca de la seguridad y la serialización. Use SecurityPermission con la marca SerializationFormatter especificada para ver o modificar los datos de instancia de objeto.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- code security, serialization
- serialization, security
- secure coding, serialization
- security [.NET Framework], serialization
ms.assetid: b921bc94-bd3a-4c91-9ede-2c8d4f78ea9a
ms.openlocfilehash: 79952ceee4c8b771aaadd4fc97a547bc65136770
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281269"
---
# <a name="security-and-serialization"></a>Seguridad y serialización
Como la serialización puede permitir que otro código vea o modifique datos de instancias de objeto que de otra forma podrían estar inaccesibles, se requiere un permiso especial del código que realiza la serialización: <xref:System.Security.Permissions.SecurityPermission> con la marca <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter> especificada. De acuerdo con la directiva predeterminada, no se concede este permiso al código descargado de Internet o de la intranet; únicamente el código del equipo local tiene garantizado este permiso.  
  
 Normalmente, se serializan todos los campos de una instancia de objeto, lo que significa que los datos se representan en los datos serializados de la instancia. Es posible que el código que puede interpretar el formato determine cuáles son los valores de datos, independientemente de la accesibilidad del miembro. De forma similar, la deserialización extrae datos de la representación serializada y establece el estado del objeto directamente, de nuevo independientemente de las reglas de accesibilidad.  
  
 Cualquier objeto que pueda contener datos confidenciales de seguridad debe hacerse no serializable, si es posible. Si debe ser serializable, intente especificar que los campos concretos que contienen datos confidenciales sean no serializables. Si esto no es posible, tenga en cuenta que estos datos se expondrán a cualquier código que tenga permiso para serializar y asegúrese de que ningún código malintencionado pueda obtener este permiso.  
  
 La interfaz <xref:System.Runtime.Serialization.ISerializable> está pensada que solo la infraestructura de serialización la utilice. Sin embargo, si no está protegida, existe el riesgo potencial de que pueda mostrar información confidencial. Si proporciona una serialización personalizada mediante la implementación de **ISerializable**, asegúrese de tomar las siguientes precauciones:  
  
- El método <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> debe protegerse explícitamente, bien exigiendo que **SecurityPermission** tenga el permiso **SerializationFormatter** especificado o bien asegurándose de que no se publica información confidencial con el resultado del método. Por ejemplo:  
  
    ```vb  
    Public Overrides<SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)>  _  
    Sub GetObjectData(info As SerializationInfo, context As StreamingContext)  
    End Sub  
    ```  
  
    ```csharp  
    [SecurityPermissionAttribute(SecurityAction.Demand,SerializationFormatter
    =true)]  
    public override void GetObjectData(SerializationInfo info,
    StreamingContext context)  
    {  
    }  
    ```  
  
- El constructor especial que se usa para la serialización también debe realizar una validación de entrada exhaustiva y debe ser de tipo protegido o privado para ayudar a la protección contra el uso indebido por parte de código malintencionado. Debe imponer las mismas comprobaciones de seguridad y los mismos permisos que se requieren para obtener una instancia de esta clase por otros medios, como la creación explícita de la clase o la creación indirecta a través de algún tipo de generador.  
  
## <a name="see-also"></a>Consulte también

- [Instrucciones de codificación segura](../../standard/security/secure-coding-guidelines.md)
