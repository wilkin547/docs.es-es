---
title: Seguridad y serialización
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
ms.openlocfilehash: 634388e3920e0b9dbee85aa3ea555471cee604ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181116"
---
# <a name="security-and-serialization"></a><span data-ttu-id="8d6e5-102">Seguridad y serialización</span><span class="sxs-lookup"><span data-stu-id="8d6e5-102">Security and Serialization</span></span>
<span data-ttu-id="8d6e5-103">Como la serialización puede permitir que otro código vea o modifique datos de instancias de objeto que de otra forma podrían estar inaccesibles, se requiere un permiso especial del código que realiza la serialización: <xref:System.Security.Permissions.SecurityPermission> con la marca <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter> especificada.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-103">Because serialization can allow other code to see or modify object instance data that would otherwise be inaccessible, a special permission is required of code performing serialization: <xref:System.Security.Permissions.SecurityPermission> with the <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter> flag specified.</span></span> <span data-ttu-id="8d6e5-104">De acuerdo con la directiva predeterminada, no se concede este permiso al código descargado de Internet o de la intranet; únicamente el código del equipo local tiene garantizado este permiso.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-104">Under default policy, this permission is not given to Internet-downloaded or intranet code; only code on the local computer is granted this permission.</span></span>  
  
 <span data-ttu-id="8d6e5-105">Normalmente, se serializan todos los campos de una instancia de objeto, lo que significa que los datos se representan en los datos serializados de la instancia.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-105">Normally, all fields of an object instance are serialized, meaning that data is represented in the serialized data for the instance.</span></span> <span data-ttu-id="8d6e5-106">Es posible que el código que puede interpretar el formato determine cuáles son los valores de datos, independientemente de la accesibilidad del miembro.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-106">It is possible for code that can interpret the format to determine what the data values are, independent of the accessibility of the member.</span></span> <span data-ttu-id="8d6e5-107">De forma similar, la deserialización extrae datos de la representación serializada y establece el estado del objeto directamente, de nuevo independientemente de las reglas de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-107">Similarly, deserialization extracts data from the serialized representation and sets object state directly, again irrespective of accessibility rules.</span></span>  
  
 <span data-ttu-id="8d6e5-108">Cualquier objeto que pueda contener datos confidenciales de seguridad debe hacerse no serializable, si es posible.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-108">Any object that could contain security-sensitive data should be made nonserializable, if possible.</span></span> <span data-ttu-id="8d6e5-109">Si debe ser serializable, intente especificar que los campos concretos que contienen datos confidenciales sean no serializables.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-109">If it must be serializable, try to make specific fields that hold sensitive data nonserializable.</span></span> <span data-ttu-id="8d6e5-110">Si esto no es posible, tenga en cuenta que estos datos se expondrán a cualquier código que tenga permiso para serializar y asegúrese de que ningún código malintencionado pueda obtener este permiso.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-110">If this cannot be done, be aware that this data will be exposed to any code that has permission to serialize, and make sure that no malicious code can get this permission.</span></span>  
  
 <span data-ttu-id="8d6e5-111">La interfaz <xref:System.Runtime.Serialization.ISerializable> está pensada que solo la infraestructura de serialización la utilice.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-111">The <xref:System.Runtime.Serialization.ISerializable> interface is intended for use only by the serialization infrastructure.</span></span> <span data-ttu-id="8d6e5-112">Sin embargo, si no está protegida, existe el riesgo potencial de que pueda mostrar información confidencial.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-112">However, if unprotected, it can potentially release sensitive information.</span></span> <span data-ttu-id="8d6e5-113">Si proporciona una serialización personalizada mediante la implementación de **ISerializable**, asegúrese de tomar las siguientes precauciones:</span><span class="sxs-lookup"><span data-stu-id="8d6e5-113">If you provide custom serialization by implementing **ISerializable**, make sure you take the following precautions:</span></span>  
  
- <span data-ttu-id="8d6e5-114">El método <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> debe protegerse explícitamente, bien exigiendo que **SecurityPermission** tenga el permiso **SerializationFormatter** especificado o bien asegurándose de que no se publica información confidencial con el resultado del método.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-114">The <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> method should be explicitly secured either by demanding the **SecurityPermission** with **SerializationFormatter** permission specified or by making sure that no sensitive information is released with the method output.</span></span> <span data-ttu-id="8d6e5-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8d6e5-115">For example:</span></span>  
  
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
  
- <span data-ttu-id="8d6e5-116">El constructor especial que se usa para la serialización también debe realizar una validación de entrada exhaustiva y debe ser de tipo protegido o privado para ayudar a la protección contra el uso indebido por parte de código malintencionado.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-116">The special constructor used for serialization should also perform thorough input validation and should be either protected or private to help protect against misuse by malicious code.</span></span> <span data-ttu-id="8d6e5-117">Debe imponer las mismas comprobaciones de seguridad y los mismos permisos que se requieren para obtener una instancia de esta clase por otros medios, como la creación explícita de la clase o la creación indirecta a través de algún tipo de generador.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-117">It should enforce the same security checks and permissions required to obtain an instance of such a class by any other means, such as explicitly creating the class or indirectly creating it through some kind of factory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d6e5-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d6e5-118">See also</span></span>

- [<span data-ttu-id="8d6e5-119">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="8d6e5-119">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
