---
title: Controlar la serialización y la deserialización con SerializationBinder
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e41308de617fc02471ac2cb9769ec6e90e665e0b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="controlling-serialization-and-deserialization-with-serializationbinder"></a><span data-ttu-id="02bd3-102">Controlar la serialización y la deserialización con SerializationBinder</span><span class="sxs-lookup"><span data-stu-id="02bd3-102">Controlling Serialization and Deserialization with SerializationBinder</span></span>
<span data-ttu-id="02bd3-103">Durante la serialización, un formateador transmite la información necesaria para crear una instancia de un objeto con el tipo y la versión correctos.</span><span class="sxs-lookup"><span data-stu-id="02bd3-103">During serialization, a formatter transmits the information required to create an instance of an object of the correct type and version.</span></span> <span data-ttu-id="02bd3-104">Por lo general, esta información incluye el nombre de tipo completo y el nombre de ensamblado del objeto.</span><span class="sxs-lookup"><span data-stu-id="02bd3-104">This information generally includes the full type name and assembly name of the object.</span></span> <span data-ttu-id="02bd3-105">De forma predeterminada, la deserialización usa esta información para crear una instancia de un objeto idéntico.</span><span class="sxs-lookup"><span data-stu-id="02bd3-105">By default, deserialization uses this information to create an instance of an identical object.</span></span> <span data-ttu-id="02bd3-106">Puede que algunos usuarios tengan que controlar qué clase desean serializar y deserializar, bien porque la clase original no exista en el equipo que realiza la deserialización, porque la clase original se haya movido entre los ensamblados, o bien porque sea necesaria una versión diferente de la clase en el servidor y en el cliente.</span><span class="sxs-lookup"><span data-stu-id="02bd3-106">Some users may need to control which class to serialize and deserialize, either because the original class may not exist on the machine performing deserialization, the original class has moved between assemblies, or a different version of the class is required on the server and client.</span></span> <span data-ttu-id="02bd3-107">Para obtener más información, consulte [uso de enlazador de serialización](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md).</span><span class="sxs-lookup"><span data-stu-id="02bd3-107">For more information, see [Usage of Serialization Binder](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="02bd3-108">Esta funcionalidad solo está disponible al usar <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> o <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="02bd3-108">This functionality is only available when using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> or the <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span>  
  
## <a name="using-serializationbinder"></a><span data-ttu-id="02bd3-109">Usar SerializationBinder</span><span class="sxs-lookup"><span data-stu-id="02bd3-109">Using SerializationBinder</span></span>  
 <span data-ttu-id="02bd3-110"><xref:System.Runtime.Serialization.SerializationBinder> es una clase abstracta usada para controlar los tipos reales empleados durante la serialización y la deserialización.</span><span class="sxs-lookup"><span data-stu-id="02bd3-110"><xref:System.Runtime.Serialization.SerializationBinder> is an abstract class used to control the actual types used during serialization and deserialization.</span></span> <span data-ttu-id="02bd3-111">Para controlar los tipos usados durante la serialización y la deserialización, derive una clase de <xref:System.Runtime.Serialization.SerializationBinder> e invalide los métodos <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> y <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)>.</span><span class="sxs-lookup"><span data-stu-id="02bd3-111">To control the types used during serialization and deserialization, derive a class from <xref:System.Runtime.Serialization.SerializationBinder> and override the <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> and <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> methods.</span></span> <span data-ttu-id="02bd3-112">El método <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> toma una clase <xref:System.Type> y devuelve un nombre de tipo y ensamblado.</span><span class="sxs-lookup"><span data-stu-id="02bd3-112">The <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> method takes a <xref:System.Type> and returns an assembly and type name.</span></span> <span data-ttu-id="02bd3-113">El método <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> toma un nombre de tipo y ensamblado y devuelve una clase <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="02bd3-113">The <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> method takes an assembly and type name and returns a <xref:System.Type>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02bd3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="02bd3-114">See Also</span></span>  
 [<span data-ttu-id="02bd3-115">Serialización y deserialización</span><span class="sxs-lookup"><span data-stu-id="02bd3-115">Serialization and Deserialization</span></span>](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)  
 [<span data-ttu-id="02bd3-116">Uso del enlazador de serialización</span><span class="sxs-lookup"><span data-stu-id="02bd3-116">Usage of Serialization Binder</span></span>](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md)
