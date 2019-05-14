---
title: Procedimiento para detectar la disponibilidad de la red y los cambios de dirección
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: d4377115-4a76-4848-ab23-4898d65c771c
ms.openlocfilehash: 8066286f458c730671acbafd713d0cbda4218ec3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624618"
---
# <a name="how-to-detect-network-availability-and-address-changes"></a><span data-ttu-id="1a365-102">Procedimiento para detectar la disponibilidad de la red y los cambios de dirección</span><span class="sxs-lookup"><span data-stu-id="1a365-102">How to: Detect Network Availability and Address Changes</span></span>
<span data-ttu-id="1a365-103">En este ejemplo se muestra cómo detectar cambios en la dirección de red de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="1a365-103">This sample shows how to detect changes in the network address of an interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a365-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1a365-104">Example</span></span>  
  
```  
using System;  
using System.Net;  
using System.Net.NetworkInformation;  
  
namespace Examples.Net.AddressChanges  
{  
    public class NetworkingExample  
    {  
        public static void Main()  
        {  
            NetworkChange.NetworkAddressChanged += new   
             NetworkAddressChangedEventHandler(AddressChangedCallback);  
            Console.WriteLine("Listening for address changes. Press any key to exit.");  
            Console.ReadLine();  
        }  
        static void AddressChangedCallback(object sender, EventArgs e)  
        {  
  
            NetworkInterface[] adapters = NetworkInterface.GetAllNetworkInterfaces();  
            foreach(NetworkInterface n in adapters)  
            {  
                Console.WriteLine("   {0} is {1}", n.Name, n.OperationalStatus);  
            }  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1a365-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="1a365-105">Compiling the Code</span></span>  
 <span data-ttu-id="1a365-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="1a365-106">This example requires:</span></span>  
  
- <span data-ttu-id="1a365-107">Referencias al espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="1a365-107">References to the **System.Net** namespace.</span></span>
