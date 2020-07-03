---
title: Interpretar el seguimiento de red
description: Obtenga información sobre cómo usar el seguimiento para capturar las llamadas que realiza la aplicación a varios miembros de la clase System.Net en .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- TraceMode attribute
- hexidecimal data, network tracing output
- network tracing, analyzing
- protocolonly
- text, network tracing output
- includehex
ms.assetid: ad22b4b8-00af-4778-9cca-cb609ce1f8ff
ms.openlocfilehash: 7a17e4ba14d8c5fe136667c4eb5bc5b2fd7a8242
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502371"
---
# <a name="interpreting-network-tracing"></a><span data-ttu-id="51278-103">Interpretar el seguimiento de red</span><span class="sxs-lookup"><span data-stu-id="51278-103">Interpreting Network Tracing</span></span>
<span data-ttu-id="51278-104">Cuando está habilitado el seguimiento de red, puede usarlo para capturar las llamadas que la aplicación realiza a diversos miembros de clase <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="51278-104">When network tracing is enabled, you can use tracing to capture calls your application makes to various <xref:System.Net> class members.</span></span> <span data-ttu-id="51278-105">La salida de estas llamadas puede ser similar a los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="51278-105">The output from these calls may be similar to the following examples.</span></span>  
  
```output
[588]   (4357)   Entering Socket#33574638::Send()  
[588]   (4387)   Exiting Socket#33574638::Send()-> 61#61
```  
  
 <span data-ttu-id="51278-106">En el ejemplo anterior, [588] es el identificador único del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="51278-106">In the preceding example, [588] is the current thread's unique identifier.</span></span> <span data-ttu-id="51278-107">(4357) y (4387) son marcas de tiempo que indican el número de milisegundos que han transcurrido desde que se ha iniciado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="51278-107">(4357) and (4387) are timestamps denoting the number of milliseconds that have elapsed since the application started.</span></span> <span data-ttu-id="51278-108">Los datos que aparecen después de la marca de tiempo muestran la aplicación que entra y sale del método **Socket.Send**.</span><span class="sxs-lookup"><span data-stu-id="51278-108">The data following the timestamp shows the application entering and exiting the method **Socket.Send**.</span></span> <span data-ttu-id="51278-109">El objeto que ejecuta el método **Send** tiene como identificador único 33574638.</span><span class="sxs-lookup"><span data-stu-id="51278-109">The object executing the **Send** method has 33574638 as its unique identifier.</span></span> <span data-ttu-id="51278-110">El seguimiento de salida del método incluye el valor devuelto (61 en el ejemplo anterior).</span><span class="sxs-lookup"><span data-stu-id="51278-110">The method exit trace includes the return value (61 in the preceding example).</span></span>  
  
 <span data-ttu-id="51278-111">Los seguimientos de red pueden capturar el tráfico de red que se envía desde la aplicación o que se recibe en esta mediante protocolos de nivel de aplicación, como el Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="51278-111">Network traces can capture network traffic that is sent from or received by your application using application-level protocols such as Hypertext Transfer Protocol (HTTP).</span></span> <span data-ttu-id="51278-112">Estos datos se pueden capturar como texto y, opcionalmente, como datos hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="51278-112">This data can be captured as text and, optionally, hexadecimal data.</span></span> <span data-ttu-id="51278-113">Los datos hexadecimales están disponibles cuando se especifica **includehex** como valor del atributo **tracemode**.</span><span class="sxs-lookup"><span data-stu-id="51278-113">Hexadecimal data is available when you specify **includehex** as the value of the **tracemode** attribute.</span></span> <span data-ttu-id="51278-114">(Para obtener información detallada sobre este atributo, vea [Cómo: Configurar el seguimiento de red](how-to-configure-network-tracing.md)). El seguimiento del ejemplo siguiente se ha generado con **includehex**.</span><span class="sxs-lookup"><span data-stu-id="51278-114">(For detailed information about this attribute, see [How to: Configure Network Tracing](how-to-configure-network-tracing.md).) The following example trace was generated using **includehex**.</span></span>  
  
 `[1692]   (1142)   00000000 : 47 45 54 20 2F 77 70 61-64 2E 64 61 74 20 48 54 : GET /wpad.dat HT`  
  
 `[1692]   (1142)   00000010 : 54 50 2F 31 2E 31 0D 0A-48 6F 73 74 3A 20 69 74 : TP/1.1..Host: it`  
  
 `[1692]   (1142)   00000020 : 67 70 72 6F 78 79 0D 0A-43 6F 6E 6E 65 63 74 69 : gproxy..Connecti`  
  
 `[1692]   (1142)   00000030 : 6F 6E 3A 20 43 6C 6F 73-65 0D 0A 0D 0A     : on: Close....`  
  
 <span data-ttu-id="51278-115">Para omitir los datos hexadecimales, especifique **protocolonly** como valor del atributo **tracemode**.</span><span class="sxs-lookup"><span data-stu-id="51278-115">To omit hexadecimal data, specify **protocolonly** as the value for the **tracemode** attribute.</span></span> <span data-ttu-id="51278-116">En el ejemplo siguiente se muestra el seguimiento cuando se especifica **protocolonly**.</span><span class="sxs-lookup"><span data-stu-id="51278-116">The following example shows the trace when **protocolonly** is specified.</span></span>  
  
 `[2444]   (594)   Data from ConnectStream#33574638::WriteHeaders<<GET /wpad.dat HTTP/1.1`  
  
 `Host: itgproxy`  
  
 `Connection: Close`  
  
## <a name="see-also"></a><span data-ttu-id="51278-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="51278-117">See also</span></span>

- [<span data-ttu-id="51278-118">Habilitar el seguimiento de red</span><span class="sxs-lookup"><span data-stu-id="51278-118">Enabling Network Tracing</span></span>](enabling-network-tracing.md)
- [<span data-ttu-id="51278-119">Cómo: Configurar el seguimiento de red</span><span class="sxs-lookup"><span data-stu-id="51278-119">How to: Configure Network Tracing</span></span>](how-to-configure-network-tracing.md)
- [<span data-ttu-id="51278-120">Network Tracing in the .NET Framework (Seguimiento de red en .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="51278-120">Network Tracing in the .NET Framework</span></span>](network-tracing.md)
