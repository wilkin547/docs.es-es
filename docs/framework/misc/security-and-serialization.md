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
# <a name="security-and-serialization"></a><span data-ttu-id="ee8ca-104">Seguridad y serialización</span><span class="sxs-lookup"><span data-stu-id="ee8ca-104">Security and Serialization</span></span>
<span data-ttu-id="ee8ca-105">Como la serialización puede permitir que otro código vea o modifique datos de instancias de objeto que de otra forma podrían estar inaccesibles, se requiere un permiso especial del código que realiza la serialización: <xref:System.Security.Permissions.SecurityPermission> con la marca <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter> especificada.</span><span class="sxs-lookup"><span data-stu-id="ee8ca-105">Because serialization can allow other code to see or modify object instance data that would otherwise be inaccessible, a special permission is required of code performing serialization: <xref:System.Security.Permissions.SecurityPermission> with the <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter> flag specified.</span></span> <span data-ttu-id="ee8ca-106">De acuerdo con la directiva predeterminada, no se concede este permiso al código descargado de Internet o de la intranet; únicamente el código del equipo local tiene garantizado este permiso.</span><span class="sxs-lookup"><span data-stu-id="ee8ca-106">Under default policy, this permission is not given to Internet-downloaded or intranet code; only code on the local computer is granted this permission.</span></span>  
  
 <span data-ttu-id="ee8ca-107">Normalmente, se serializan todos los campos de una instancia de objeto, lo que significa que los datos se representan en los datos serializados de la instancia.</span><span class="sxs-lookup"><span data-stu-id="ee8ca-107">Normally, all fields of an object instance are serialized, meaning that data is represented in the serialized data for the instance.</span></span> <span data-ttu-id="ee8ca-108">Es posible que el código que puede interpretar el formato determine cuáles son los valores de datos, independientemente de la accesibilidad del miembro.</span><span class="sxs-lookup"><span data-stu-id="ee8ca-108">It is possible for code that can interpret the format to determine what the data values are, independent of the accessibility of the member.</span></span> <span data-ttu-id="ee8ca-109">De forma similar, la deserialización extrae datos de la representación serializada y establece el estado del objeto directamente, de nuevo independientemente de las reglas de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="ee8ca-109">Similarly, deserialization extracts data from the serialized representation and sets object state directly, again irrespective of accessibility rules.</span></span>  
  
 <span data-ttu-id="ee8ca-110">Cualquier objeto que pueda contener datos confidenciales de seguridad debe hacerse no serializable, si es posible.</span><span class="sxs-lookup"><span data-stu-id="ee8ca-110">Any object that could contain security-sensitive data should be made nonserializable, if possible.</span></span> <span data-ttu-id="ee8ca-111">Si debe ser serializable, intente especificar que los campos concretos que contienen datos confidenciales sean no serializables.</span><span class="sxs-lookup"><span data-stu-id="ee8ca-111">If it must be serializable, try to make specific fields that hold sensitive data nonserializable.</span></span> <span data-ttu-id="ee8ca-112">Si esto no es posible, tenga en cuenta que estos datos se expondrán a cualquier código que tenga permiso para serializar y asegúrese de que ningún código malintencionado pueda obtener este permiso.</span><span class="sxs-lookup"><span data-stu-id="ee8ca-112">If this cannot be done, be aware that this data will be exposed to any code that has permission to serialize, and make sure that no malicious code can get this permission.</span></span>  
  
 <span data-ttu-id="ee8ca-113">La interfaz <xref:System.Runtime.Serialization.ISerializable> está pensada que solo la infraestructura de serialización la utilice.</span><span class="sxs-lookup"><span data-stu-id="ee8ca-113">The <xref:System.Runtime.Serialization.ISerializable> interface is intended for use only by the serialization infrastructure.</span></span> <span data-ttu-id="ee8ca-114">Sin embargo, si no está protegida, existe el riesgo potencial de que pueda mostrar información confidencial.</span><span class="sxs-lookup"><span data-stu-id="ee8ca-114">However, if unprotected, it can potentially release sensitive information.</span></span> <span data-ttu-id="ee8ca-115">Si proporciona una serialización personalizada mediante la implementación de **ISerializable**, asegúrese de tomar las siguientes precauciones:</span><span class="sxs-lookup"><span data-stu-id="ee8ca-115">If you provide custom serialization by implementing **ISerializable**, make sure you take the following precautions:</span></span>  
  
- <span data-ttu-id="ee8ca-116">El método <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> debe protegerse explícitamente, bien exigiendo que **SecurityPermission** tenga el permiso **SerializationFormatter** especificado o bien asegurándose de que no se publica información confidencial con el resultado del método.</span><span class="sxs-lookup"><span data-stu-id="ee8ca-116">The <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> method should be explicitly secured either by demanding the **SecurityPermission** with **SerializationFormatter** permission specified or by making sure that no sensitive information is released with the method output.</span></span> <span data-ttu-id="ee8ca-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ee8ca-117">For example:</span></span>  
  
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
  
- <span data-ttu-id="ee8ca-118">El constructor especial que se usa para la serialización también debe realizar una validación de entrada exhaustiva y debe ser de tipo protegido o privado para ayudar a la protección contra el uso indebido por parte de código malintencionado.</span><span class="sxs-lookup"><span data-stu-id="ee8ca-118">The special constructor used for serialization should also perform thorough input validation and should be either protected or private to help protect against misuse by malicious code.</span></span> <span data-ttu-id="ee8ca-119">Debe imponer las mismas comprobaciones de seguridad y los mismos permisos que se requieren para obtener una instancia de esta clase por otros medios, como la creación explícita de la clase o la creación indirecta a través de algún tipo de generador.</span><span class="sxs-lookup"><span data-stu-id="ee8ca-119">It should enforce the same security checks and permissions required to obtain an instance of such a class by any other means, such as explicitly creating the class or indirectly creating it through some kind of factory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee8ca-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ee8ca-120">See also</span></span>

- [<span data-ttu-id="ee8ca-121">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="ee8ca-121">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
