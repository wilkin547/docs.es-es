---
title: Niveles de confianza de seguridad para acceder a los recursos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb5be924-317d-4d69-b33a-3d18ecfb9d6e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d6fe8902021d6585434c2dcdfa42784d59818157
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="security-trust-levels-in-accessing-resources"></a><span data-ttu-id="1ea87-102">Niveles de confianza de seguridad para acceder a los recursos</span><span class="sxs-lookup"><span data-stu-id="1ea87-102">Security Trust Levels in Accessing Resources</span></span>
<span data-ttu-id="1ea87-103">En este tema se discute cómo el acceso está restringido en los tipos de recursos que <xref:System.Transactions> expone.</span><span class="sxs-lookup"><span data-stu-id="1ea87-103">This topic discusses how access is restricted on the types of resources that <xref:System.Transactions> exposes.</span></span>  
  
 <span data-ttu-id="1ea87-104">Hay tres niveles principales de confianza para <xref:System.Transactions>.</span><span class="sxs-lookup"><span data-stu-id="1ea87-104">There are three main levels of trust for <xref:System.Transactions>.</span></span> <span data-ttu-id="1ea87-105">Los niveles de confianza se definen dependiendo de los tipos de recursos que <xref:System.Transactions> expone y el nivel de confianza que se debería exigir para tener acceso a esos recursos.</span><span class="sxs-lookup"><span data-stu-id="1ea87-105">The trust levels are defined based on the types of resources that <xref:System.Transactions> exposes, and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="1ea87-106">Los recursos a los que <xref:System.Transactions> proporciona acceso, son la memoria del sistema, recursos amplios de proceso compartido y los recursos para todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="1ea87-106">The resources that <xref:System.Transactions> provides access to are system memory, shared process wide resources, and system wide resources.</span></span> <span data-ttu-id="1ea87-107">Los niveles son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1ea87-107">The levels are:</span></span>  
  
-   <span data-ttu-id="1ea87-108">**AllowPartiallyTrustedCallers** (APTCA) para las aplicaciones que usan las transacciones dentro de un único dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1ea87-108">**AllowPartiallyTrustedCallers** (APTCA) for applications using transactions within a single application domain.</span></span>  
  
-   <span data-ttu-id="1ea87-109">**DistributedTransactionPermission** (DTP) para aplicaciones que utilicen transacciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="1ea87-109">**DistributedTransactionPermission** (DTP) for applications using distributed transactions.</span></span>  
  
-   <span data-ttu-id="1ea87-110">Plena confianza para los recursos duraderos, aplicaciones de gestión de la configuración y las aplicaciones interoperativas heredadas.</span><span class="sxs-lookup"><span data-stu-id="1ea87-110">Full trust for durable resources, configuration management applications, and legacy interop applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ea87-111">No se debería llamar a cualquiera de las interfaces de inscripción con contextos suplantados.</span><span class="sxs-lookup"><span data-stu-id="1ea87-111">You should not call any of the enlistment interfaces with impersonated contexts.</span></span>  
  
## <a name="trust-levels"></a><span data-ttu-id="1ea87-112">Niveles de confianza</span><span class="sxs-lookup"><span data-stu-id="1ea87-112">Trust Levels</span></span>  
  
### <a name="aptca-partial-trust"></a><span data-ttu-id="1ea87-113">APTCA (confianza parcial)</span><span class="sxs-lookup"><span data-stu-id="1ea87-113">APTCA (Partial Trust)</span></span>  
 <span data-ttu-id="1ea87-114">El <xref:System.Transactions> ensamblado puede llamarse mediante código de confianza parcial porque se ha marcado con el **AllowPartiallyTrustedCallers** atributo (APTCA).</span><span class="sxs-lookup"><span data-stu-id="1ea87-114">The <xref:System.Transactions> assembly can be called by partially trusted code because it has been marked with the **AllowPartiallyTrustedCallers** attribute (APTCA).</span></span> <span data-ttu-id="1ea87-115">Este atributo básicamente quita la parte implícita <xref:System.Security.Permissions.SecurityAction.LinkDemand> para el **FullTrust** conjunto de permisos en caso contrario, colocan automáticamente en cada método público accesible de cada tipo.</span><span class="sxs-lookup"><span data-stu-id="1ea87-115">This attribute essentially removes the implicit <xref:System.Security.Permissions.SecurityAction.LinkDemand> for the **FullTrust** permission set that is otherwise automatically placed on each publicly accessible method in each type.</span></span> <span data-ttu-id="1ea87-116">Sin embargo, algunos tipos y miembros siguen necesitando permisos más firmes.</span><span class="sxs-lookup"><span data-stu-id="1ea87-116">However, some types and members still require stronger permissions.</span></span>  
  
 <span data-ttu-id="1ea87-117">El atributo APTCA permite a las aplicaciones utilizar las transacciones en confianza parcial dentro de un dominio de aplicación único.</span><span class="sxs-lookup"><span data-stu-id="1ea87-117">The APTCA attribute enables applications to use transactions in partial trust within a single application domain.</span></span> <span data-ttu-id="1ea87-118">Esto habilita las transacciones no escalonadas y las inscripciones volátiles que se pueden utilizar para el control de errores.</span><span class="sxs-lookup"><span data-stu-id="1ea87-118">This enables non-escalated transactions and volatile enlistments that can be used for error handling.</span></span> <span data-ttu-id="1ea87-119">Un ejemplo de esto es una tabla hash llevada a cabo y una aplicación que lo utiliza.</span><span class="sxs-lookup"><span data-stu-id="1ea87-119">One example of this is a transacted hash table and an application that uses it.</span></span> <span data-ttu-id="1ea87-120">Los datos se pueden agregar a y quitar de la tabla hash bajo una transacción única.</span><span class="sxs-lookup"><span data-stu-id="1ea87-120">Data can be added to and removed from the hash table under a single transaction.</span></span> <span data-ttu-id="1ea87-121">Si se deshace la transacción después, se pueden deshacer todos los cambios realizados a la tabla hash bajo esa transacción.</span><span class="sxs-lookup"><span data-stu-id="1ea87-121">If the transaction is later rolled back, all of the changes made to the hash table under that transaction can be undone.</span></span>  
  
### <a name="distributedtransactionpermission-dtp"></a><span data-ttu-id="1ea87-122">DistributedTransactionPermission (DTP)</span><span class="sxs-lookup"><span data-stu-id="1ea87-122">DistributedTransactionPermission (DTP)</span></span>  
 <span data-ttu-id="1ea87-123">Cuando se realiza una escalada una transacción <xref:System.Transactions> para ser administrada por MSDTC, <xref:System.Transactions> exige (DTP) <xref:System.Transactions.DistributedTransactionPermission> para crear la transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="1ea87-123">When a <xref:System.Transactions> transaction is escalated to be managed by MSDTC, <xref:System.Transactions> demands the <xref:System.Transactions.DistributedTransactionPermission> (DTP) to create the distributed transaction.</span></span> <span data-ttu-id="1ea87-124">Esto significa que el código que produce la transacción que ha de realizar una escalada (como a través de serialización o las inscripciones adicionales duraderas) necesitaría ser concedido DTP.</span><span class="sxs-lookup"><span data-stu-id="1ea87-124">This means that the code that causes the transaction to be escalated (such as through serialization or additional durable enlistments) would need to be granted DTP.</span></span> <span data-ttu-id="1ea87-125">El código que originalmente creó la transacción <xref:System.Transactions> necesariamente no necesita poseer este permiso.</span><span class="sxs-lookup"><span data-stu-id="1ea87-125">The code that originally created the <xref:System.Transactions> transaction does not necessarily need to possess this permission.</span></span>  
  
### <a name="fulltrust-link-demands"></a><span data-ttu-id="1ea87-126">Peticiones de vínculo de FullTrust</span><span class="sxs-lookup"><span data-stu-id="1ea87-126">FullTrust Link Demands</span></span>  
 <span data-ttu-id="1ea87-127">Se piensa que este nivel de permisos restringe aplicaciones que están escribiendo en los recursos duraderos.</span><span class="sxs-lookup"><span data-stu-id="1ea87-127">This permission level is intended to restrict applications that are writing to durable resources.</span></span> <span data-ttu-id="1ea87-128">En el error, la aplicación necesita poder recuperarse con el administrador de transacciones para determinar el último resultado de la transacción, para que pueda actualizar los datos permanentes.</span><span class="sxs-lookup"><span data-stu-id="1ea87-128">Upon failure, the application needs to be able to recover with the transaction manager to determine the final outcome of the transaction, so that it can update permanent data.</span></span> <span data-ttu-id="1ea87-129">Este tipo de aplicación es conocido como un administrador de origen duradero.</span><span class="sxs-lookup"><span data-stu-id="1ea87-129">This type of application is known as a durable source manager.</span></span> <span data-ttu-id="1ea87-130">Un ejemplo clásico de este tipo de aplicación es SQL.</span><span class="sxs-lookup"><span data-stu-id="1ea87-130">A classic example of this type of application is SQL.</span></span>  
  
 <span data-ttu-id="1ea87-131">Para habilitar la recuperación, este tipo de aplicación tiene la capacidad de utilizar permanentemente los recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="1ea87-131">To enable recovery, this type of application has the ability to permanently consume system resources.</span></span> <span data-ttu-id="1ea87-132">Esto sucede porque el administrador de transacciones recuperable debe recordar transacciones que se han confirmado hasta que pueda confirmar que todos los administradores de recursos duraderos que están participando en la transacción han recibido el resultado.</span><span class="sxs-lookup"><span data-stu-id="1ea87-132">This is because the recoverable transaction manager must remember transactions that have committed until it can confirm that all durable resource managers that are participating in the transaction have received the outcome.</span></span> <span data-ttu-id="1ea87-133">Por consiguiente, este tipo de aplicación requiere la plena confianza y no se ejecuta a menos que se haya permitido ese nivel de confianza.</span><span class="sxs-lookup"><span data-stu-id="1ea87-133">Therefore, this type of application requires full trust and should not be run unless that level of trust has been granted.</span></span>  
  
 <span data-ttu-id="1ea87-134">Para obtener más información sobre inscripciones duraderas y recuperación, consulte el [dar de alta los recursos como los participantes en una transacción](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) y [realizar recuperación](../../../../docs/framework/data/transactions/performing-recovery.md) temas.</span><span class="sxs-lookup"><span data-stu-id="1ea87-134">For more information on durable enlistments and recovery, see the [Enlisting Resources as Participants in a Transaction](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) and [Performing Recovery](../../../../docs/framework/data/transactions/performing-recovery.md) topics.</span></span>  
  
 <span data-ttu-id="1ea87-135">También exigen a las aplicaciones que realizan el trabajo de la interoperabilidad heredado con COM+ que tengan la plena confianza.</span><span class="sxs-lookup"><span data-stu-id="1ea87-135">Applications that perform legacy interop work with COM+ are also required to have full trust.</span></span>  
  
 <span data-ttu-id="1ea87-136">La siguiente es una lista de tipos y miembros que no se puede llamados parcialmente el código de confianza porque se decoran con el **FullTrust** atributo de seguridad declarativa:</span><span class="sxs-lookup"><span data-stu-id="1ea87-136">The following is a list of types and members that are not callable by partially trusted code because they are decorated with the **FullTrust** declarative security attribute:</span></span>  
  
 `PermissionSetAttribute(SecurityAction.LinkDemand, Name := "FullTrust")`  
  
-   <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType>  
  
-   <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A>  
  
-   <xref:System.Transactions.TransactionInterop>  
  
-   <xref:System.Transactions.TransactionManager.DistributedTransactionStarted>  
  
-   <xref:System.Transactions.HostCurrentTransactionCallback>  
  
-   <xref:System.Transactions.TransactionManager.Reenlist%2A>  
  
-   <xref:System.Transactions.TransactionManager.RecoveryComplete%2A>  
  
-   <xref:System.Transactions.TransactionScope.%23ctor%28System.Transactions.TransactionScopeOption%2CSystem.Transactions.TransactionOptions%2CSystem.Transactions.EnterpriseServicesInteropOption%29>  
  
 <span data-ttu-id="1ea87-137">Solo se requiere para poseer el llamador inmediato del **FullTrust** permiso establecido para usar los métodos o los tipos anteriores.</span><span class="sxs-lookup"><span data-stu-id="1ea87-137">Only the immediate caller is required to possess the **FullTrust** permission set to use the above types or methods.</span></span>
