---
title: Ejemplo de compensación personalizada
ms.date: 03/30/2017
ms.assetid: 385920da-9284-44bf-9fe9-0d87c7478ec5
ms.openlocfilehash: 55161a46bebca2cce41803ca405cb2b1df57b3fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514329"
---
# <a name="custom-compensation-sample"></a><span data-ttu-id="a7f07-102">Ejemplo de compensación personalizada</span><span class="sxs-lookup"><span data-stu-id="a7f07-102">Custom Compensation Sample</span></span>
<span data-ttu-id="a7f07-103">En este ejemplo se muestra cómo utilizar <xref:System.Activities.Statements.CompensableActivity> y su controlador de compensación para definir lógica de compensación personalizada.</span><span class="sxs-lookup"><span data-stu-id="a7f07-103">This sample shows how to use <xref:System.Activities.Statements.CompensableActivity> and its compensation handler to define custom compensation logic.</span></span> <span data-ttu-id="a7f07-104">El escenario modelado en este ejemplo es una agencia de alquiler de camiones.</span><span class="sxs-lookup"><span data-stu-id="a7f07-104">The scenario modeled in this sample is a Truck Rental Agency.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="a7f07-105">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7f07-105">Sample Details</span></span>  
 <span data-ttu-id="a7f07-106">Los pasos simulados son:</span><span class="sxs-lookup"><span data-stu-id="a7f07-106">The steps simulated are:</span></span>  
  
1.  <span data-ttu-id="a7f07-107">El usuario solicita ofertas de alquiler de camiones para una fecha determinada.</span><span class="sxs-lookup"><span data-stu-id="a7f07-107">The user requests truck rental quotes for a given date.</span></span>  
  
2.  <span data-ttu-id="a7f07-108">Se establece contacto con tres empresas de camiones y se proporcionan tres ofertas.</span><span class="sxs-lookup"><span data-stu-id="a7f07-108">Three truck companies are contacted and the three quotes are provided.</span></span>  
  
3.  <span data-ttu-id="a7f07-109">El usuario selecciona una oferta de camión y realiza el pedido con tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="a7f07-109">The user selects one truck quote and proceeds to order by credit card.</span></span>  
  
4.  <span data-ttu-id="a7f07-110">La aplicación cancela las otras dos ofertas de camión.</span><span class="sxs-lookup"><span data-stu-id="a7f07-110">The application cancels the other two truck quotes.</span></span>  
  
5.  <span data-ttu-id="a7f07-111">La aplicación carga una cuota de servicio que no se puede reembolsar en las cuentas no bonificadas si se produce una cancelación en un periodo inferior a 10 días antes de la fecha de reserva.</span><span class="sxs-lookup"><span data-stu-id="a7f07-111">The application charges a service fee that is non-refundable for non-premium accounts if cancelation happens 10 days or less prior to the reservation date.</span></span>  
  
6.  <span data-ttu-id="a7f07-112">La aplicación carga la cuota de alquiler del camión.</span><span class="sxs-lookup"><span data-stu-id="a7f07-112">The application charges the truck rental fee.</span></span>  
  
7.  <span data-ttu-id="a7f07-113">La aplicación espera hasta la fecha de la reserva o hasta que el cliente decida cancelar la reserva, lo que suceda primero.</span><span class="sxs-lookup"><span data-stu-id="a7f07-113">The application waits until the reservation date or until the customer decided to cancel the reservation, whichever comes first.</span></span>  
  
8.  <span data-ttu-id="a7f07-114">Si el cliente cancela la reserva, se ejecuta la lógica de compensación personalizada de <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> según la siguiente lógica:</span><span class="sxs-lookup"><span data-stu-id="a7f07-114">If the customer cancels the reservation, the <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> custom compensation logic runs according to the following logic:</span></span>  
  
    1.  <span data-ttu-id="a7f07-115">Si el cliente tiene una cuenta no bonificada y faltan menos de 10 días para la fecha de reserva, se sigue cobrando la cuota de servicio; en caso contrario, la aplicación reembolsa la cuota de servicio.</span><span class="sxs-lookup"><span data-stu-id="a7f07-115">If the customer has a non-premium account and it is less than 10 days prior to the reservation date, then the service fee is still charged; otherwise, the application refunds the service fee.</span></span>  
  
    2.  <span data-ttu-id="a7f07-116">El resto de las actividades compensables (el pedido de camión + la cuota de pedido de camión) se ejecutan según la lógica de compensación predeterminada, que compensa en orden inverso a la ejecución.</span><span class="sxs-lookup"><span data-stu-id="a7f07-116">The rest of the compensable activities (truck order + truck order fee) are run according to the default compensation logic, which is to compensate in reverse order of execution.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a7f07-117">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7f07-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a7f07-118">Abra el archivo de solución CustomCompensation.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7f07-118">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CustomCompensation.sln solution.</span></span> <span data-ttu-id="a7f07-119">Se encuentra en el directorio \WF\Basic\Compensation\CustomCompensation.</span><span class="sxs-lookup"><span data-stu-id="a7f07-119">It is located in the \WF\Basic\Compensation\CustomCompensation directory.</span></span>  
  
2.  <span data-ttu-id="a7f07-120">Presione Ctrl+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="a7f07-120">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="a7f07-121">Presione CTRL+F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a7f07-121">Press CTRL + F5 to run the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a7f07-122">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a7f07-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a7f07-123">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a7f07-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a7f07-124">Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a7f07-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a7f07-125">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a7f07-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CustomCompensation`