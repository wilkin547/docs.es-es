---
title: Uso del enlazador de serialización
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: 061afb94d97e3d8a1222e6de9932344fb3ebbe59
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294903"
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="50dfc-102">Uso del enlazador de serialización</span><span class="sxs-lookup"><span data-stu-id="50dfc-102">Usage of Serialization Binder</span></span>

<span data-ttu-id="50dfc-103">Este ejemplo muestra cómo utilizar <xref:System.Runtime.Serialization.SerializationBinder> para cambiar la versión de un tipo genérico cuando se serializa.</span><span class="sxs-lookup"><span data-stu-id="50dfc-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="50dfc-104">Muestra</span><span class="sxs-lookup"><span data-stu-id="50dfc-104">Demonstrates</span></span>  

 <span data-ttu-id="50dfc-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="50dfc-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="50dfc-106">Discusión</span><span class="sxs-lookup"><span data-stu-id="50dfc-106">Discussion</span></span>  

 <span data-ttu-id="50dfc-107">Este ejemplo muestra cómo dos entidades que tienen como destino versiones diferentes del .NET Framework pueden comunicarse mediante el formateador binario y el enlazador de serialización.</span><span class="sxs-lookup"><span data-stu-id="50dfc-107">This sample shows how two entities that are targeting different versions of the .NET Framework can communicate using the binary formatter and the serialization binder.</span></span>  
  
<span data-ttu-id="50dfc-108">Este ejemplo se desarrolló con .NET Remoting.</span><span class="sxs-lookup"><span data-stu-id="50dfc-108">This sample was developed using .NET Remoting.</span></span> <span data-ttu-id="50dfc-109">Consta de un servidor que tiene como destino .NET Framework 4, que implementa un contrato con tipos genéricos y dos clientes diferentes, uno de destino .NET Framework 2,0 y otro de destino .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="50dfc-109">It consists of a server targeting .NET Framework 4, which implements a contract with generic types, and two different clients, one targeting .NET Framework 2.0 and another targeting .NET Framework 4.</span></span>  
  
 <span data-ttu-id="50dfc-110">El servidor asocia un objeto <xref:System.Runtime.Serialization.SerializationBinder> al formateador binario para poder cambiar la versión de los tipos de acuerdo con la serialización, de modo que ambos clientes puedan deserializar esos tipos correctamente.</span><span class="sxs-lookup"><span data-stu-id="50dfc-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="50dfc-111">Para configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="50dfc-111">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="50dfc-112">Para ejecutar el cliente, haga clic con el botón derecho en la solución, SBGenericsVTS (6 proyectos) y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="50dfc-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="50dfc-113">En **propiedades comunes**, seleccione **proyecto de inicio** y, a continuación, seleccione **proyectos de inicio múltiples**.</span><span class="sxs-lookup"><span data-stu-id="50dfc-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="50dfc-114">Seleccione **servidor** primero, **Client20** y, a continuación, **Client40**.</span><span class="sxs-lookup"><span data-stu-id="50dfc-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="50dfc-115">Seleccione la acción de **Inicio** en estos tres proyectos y deje el resto establecido en **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="50dfc-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4. <span data-ttu-id="50dfc-116">Haga clic en **Aceptar** y, a continuación, presione F5 para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="50dfc-116">Click **OK** and then press F5 to run the sample.</span></span>
