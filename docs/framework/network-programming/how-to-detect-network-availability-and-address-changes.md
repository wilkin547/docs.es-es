---
description: 'Más información acerca de: Procedimiento: para detectar la disponibilidad de la red y los cambios de dirección'
title: 'Cómo: detectar la disponibilidad de la red y los cambios de dirección'
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: d4377115-4a76-4848-ab23-4898d65c771c
ms.openlocfilehash: b9465cbfc538c551725d6510cac3c73d006b7b59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747444"
---
# <a name="how-to-detect-network-availability-and-address-changes"></a>Procedimiento para detectar la disponibilidad de la red y los cambios de dirección

En este ejemplo se muestra cómo detectar cambios en la dirección de red de una interfaz.  
  
## <a name="example"></a>Ejemplo  
  
```csharp
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
  
## <a name="compiling-the-code"></a>Compilar el código  

 Para este ejemplo se necesita:  
  
- Referencias al espacio de nombres **System.Net**.
