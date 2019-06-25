---
title: Uso del enlazador de serialización
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: 10900950b935b484053fe8e37263f0dfc25eba99
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348456"
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="e81ea-102">Uso del enlazador de serialización</span><span class="sxs-lookup"><span data-stu-id="e81ea-102">Usage of Serialization Binder</span></span>
<span data-ttu-id="e81ea-103">Este ejemplo muestra cómo utilizar <xref:System.Runtime.Serialization.SerializationBinder> para cambiar la versión de un tipo genérico cuando se serializa.</span><span class="sxs-lookup"><span data-stu-id="e81ea-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="e81ea-104">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="e81ea-104">Demonstrates</span></span>  
 <span data-ttu-id="e81ea-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="e81ea-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="e81ea-106">Discusión</span><span class="sxs-lookup"><span data-stu-id="e81ea-106">Discussion</span></span>  
 <span data-ttu-id="e81ea-107">Este ejemplo muestra cómo dos entidades que son destinatarios diferentes versiones de puede .NET Framework comunicarse utilizando el formateador binario y el enlazador de serialización.</span><span class="sxs-lookup"><span data-stu-id="e81ea-107">This sample shows how two entities that are targeting different versions of the .NET Framework can communicate using the binary formatter and the serialization binder.</span></span>  
  
<span data-ttu-id="e81ea-108">En este ejemplo se desarrolló con .NET Remoting.</span><span class="sxs-lookup"><span data-stu-id="e81ea-108">This sample was developed using .NET Remoting.</span></span> <span data-ttu-id="e81ea-109">Consta de un servidor para [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], que implementa un contrato con tipos genéricos y dos clientes diferentes, destino .NET Framework 2.0 y otro para [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e81ea-109">It consists of a server targeting [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], which implements a contract with generic types, and two different clients, one targeting .NET Framework 2.0 and another targeting [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span></span>  
  
 <span data-ttu-id="e81ea-110">El servidor asocia un objeto <xref:System.Runtime.Serialization.SerializationBinder> al formateador binario para poder cambiar la versión de los tipos de acuerdo con la serialización, de modo que ambos clientes puedan deserializar esos tipos correctamente.</span><span class="sxs-lookup"><span data-stu-id="e81ea-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e81ea-111">Para configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="e81ea-111">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="e81ea-112">Para ejecutar el cliente, haga clic en la solución, SBGenericsVTS (6 proyectos) y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e81ea-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="e81ea-113">En **propiedades comunes**, seleccione **proyecto de inicio**, a continuación, seleccione **varios proyectos de inicio**.</span><span class="sxs-lookup"><span data-stu-id="e81ea-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="e81ea-114">Seleccione **Server** primero, a continuación **Client20** y, a continuación, **Client40**.</span><span class="sxs-lookup"><span data-stu-id="e81ea-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="e81ea-115">Seleccione el **iniciar** acción para estos tres proyectos y deje el resto establecido en **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="e81ea-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4. <span data-ttu-id="e81ea-116">Haga clic en **Aceptar** y, a continuación, presione F5 para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e81ea-116">Click **OK** and then press F5 to run the sample.</span></span>
