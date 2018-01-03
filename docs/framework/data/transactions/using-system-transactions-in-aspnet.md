---
title: Usar System.Transactions en ASP.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: caa0f8cc5b98ae50e1c9d2da716dd03eb5cb4565
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-systemtransactions-in-aspnet"></a><span data-ttu-id="b4be1-102">Usar System.Transactions en ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b4be1-102">Using System.Transactions in ASP.NET</span></span>
<span data-ttu-id="b4be1-103">En este tema se describe cómo se puede usar <xref:System.Transactions> correctamente en una aplicación [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4be1-103">This topic describes how you can successfully use <xref:System.Transactions> inside an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application.</span></span>  
  
## <a name="enable-distributedtransactionpermission-in-aspnet"></a><span data-ttu-id="b4be1-104">Habilitar DistributedTransactionPermission en ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b4be1-104">Enable DistributedTransactionPermission in ASP.NET</span></span>  
 <span data-ttu-id="b4be1-105"><xref:System.Transactions> admite los llamadores de confianza parcial y se marca con el atributo **AllowPartiallyTrustedCallers** (APTCA).</span><span class="sxs-lookup"><span data-stu-id="b4be1-105"><xref:System.Transactions> supports partially trusted callers and is marked with the **AllowPartiallyTrustedCallers** attribute (APTCA).</span></span> <span data-ttu-id="b4be1-106">Los niveles de confianza para <xref:System.Transactions> se definen dependiendo de los tipos de recursos, por ejemplo, la memoria del sistema, los recursos de todo el proceso compartido, los recursos para todo el sistema y otros recursos. <xref:System.Transactions> expone dichos tipos de recursos y el nivel de confianza que se debería exigir para tener acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="b4be1-106">The trust levels for <xref:System.Transactions> are defined based on the types of resources, (for example, system memory, shared process-wide resources, system-wide resources, and other resources), that <xref:System.Transactions> exposes and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="b4be1-107">En un entorno de confianza parcial, un ensamblado sin plena confianza puede usar solo las transacciones dentro del dominio de aplicación (en este caso, el único recurso que se protege es la memoria del sistema) a menos que se permita <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="b4be1-107">In a partial-trust environment, a non-full trust assembly can only use transactions within the Application Domain (in this case, the only resource being protected is system memory), unless it is granted the <xref:System.Transactions.DistributedTransactionPermission>.</span></span>  
  
 <span data-ttu-id="b4be1-108">Se exige<xref:System.Transactions.DistributedTransactionPermission> cuando la administración de la transacción se escala para que el Coordinador de transacciones distribuidas de Microsoft (MSDTC) la administre.</span><span class="sxs-lookup"><span data-stu-id="b4be1-108"><xref:System.Transactions.DistributedTransactionPermission> is demanded whenever transaction management is escalated to be managed by the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span> <span data-ttu-id="b4be1-109">Este tipo de escenario usa recursos de todo el proceso y particularmente un recurso global, que es el espacio reservado en el registro de MSDTC.</span><span class="sxs-lookup"><span data-stu-id="b4be1-109">This kind of scenario utilizes process-wide resources and particularly a global resource, which is the reserved space in the MSDTC log.</span></span> <span data-ttu-id="b4be1-110">Un ejemplo de este uso es un front-end web con una base de datos o una aplicación que usa una base de datos como parte de los servicios que proporciona.</span><span class="sxs-lookup"><span data-stu-id="b4be1-110">An example of this usage is a Web front-end to a database or an application that uses a database as part of the services it provides.</span></span>  
  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="b4be1-111"> tiene su propio conjunto de niveles de confianza y asocia un conjunto concreto de permisos con estos niveles de confianza a través de los archivos de directivas.</span><span class="sxs-lookup"><span data-stu-id="b4be1-111"> has its own set of trust levels and associates a specific set of permissions with these trust levels through policy files.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="b4be1-112">[Niveles de confianza de ASP.NET y archivos de directivas](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1).</span><span class="sxs-lookup"><span data-stu-id="b4be1-112"> [ASP.NET Trust Levels and Policy Files](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1).</span></span> <span data-ttu-id="b4be1-113">Cuando instala inicialmente Windows SDK, ninguno de los archivos de directivas [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] predeterminados está asociado con <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="b4be1-113">When you initially install the Windows SDK, none of the default [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] policy files are associated with the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="b4be1-114">Como tal, cuando la transacción en una aplicación [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] se escala para que el MSDTC la administre, se produce un error en la extensión con <xref:System.Security.SecurityException> al exigir <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="b4be1-114">As such, when your transaction in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application is escalated to be managed by the MSDTC, the escalation fails with a <xref:System.Security.SecurityException> upon demanding the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="b4be1-115">Para habilitar la extensión de transacciones en un entorno de confianza parcial de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , debe conceder <xref:System.Transactions.DistributedTransactionPermission> en los mismos niveles de confianza predeterminados como los de <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="b4be1-115">To enable transaction escalation in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] partial trust environment, you should grant the <xref:System.Transactions.DistributedTransactionPermission> in the same default trust levels as those of <xref:System.Data.SqlClient.SqlClientPermission>.</span></span> <span data-ttu-id="b4be1-116">Puede configurar su propio nivel de confianza personalizado y archivo de directivas para admitirlo o bien modificar los archivos de directivas predeterminados, **Web_hightrust.config** y **Web_mediumtrust.config**.</span><span class="sxs-lookup"><span data-stu-id="b4be1-116">You can either configure your own custom trust level and policy file to support this, or you can modify the default policy files, which are **Web_hightrust.config** and **Web_mediumtrust.config**.</span></span>  
  
 <span data-ttu-id="b4be1-117">Para modificar los archivos de directivas, agregue un **SecurityClass** (elemento) para **DistributedTransactionPermission** a la **SecurityClasses** elemento bajo el  **PolicyLevel** elemento y agregue su correspondiente **IPermission** elemento bajo el [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** para System.Transactions.</span><span class="sxs-lookup"><span data-stu-id="b4be1-117">To modify the policy files, add a **SecurityClass** element for **DistributedTransactionPermission** to the **SecurityClasses** element under the **PolicyLevel** element and add a corresponding **IPermission** element under the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** for System.Transactions.</span></span> <span data-ttu-id="b4be1-118">Esto se muestra en el siguiente archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b4be1-118">The following configuration file demonstrates this.</span></span>  
  
```xml  
<SecurityClasses>  
   <SecurityClass Name="DistributedTransactionPermission" Description="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
...  
</SecurityClasses>  
  
<PermissionSet  
  class="NamedPermissionSet"  
  version="1"  
  Name="ASP.Net">  
     <IPermission  
        class="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
        version="1"  
        Unrestricted="true"  
     />  
...  
</PermissionSet>  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="b4be1-119"> [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , consulte [Elemento securityPolicy (Esquema de configuración de ASP.NET)](http://msdn.microsoft.com/en-us/469d8d22-d263-46bb-8400-40d8d027faba).</span><span class="sxs-lookup"><span data-stu-id="b4be1-119"> [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] security policy, see [securityPolicy Element (ASP.NET Settings Schema)](http://msdn.microsoft.com/en-us/469d8d22-d263-46bb-8400-40d8d027faba).</span></span>  
  
## <a name="dynamic-compilation"></a><span data-ttu-id="b4be1-120">Compilación dinámica</span><span class="sxs-lookup"><span data-stu-id="b4be1-120">Dynamic Compilation</span></span>  
 <span data-ttu-id="b4be1-121">Si quiere importar y usar <xref:System.Transactions> en una aplicación [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] que está compilada dinámicamente en acceso, debe colocar una referencia al ensamblado <xref:System.Transactions> en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b4be1-121">If you want to import and use <xref:System.Transactions> in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application that is dynamically compiled on access, you should place a reference to the <xref:System.Transactions> assembly in the configuration file.</span></span> <span data-ttu-id="b4be1-122">Específicamente, la referencia debe agregarse en la sección **compilation**/**assemblies** del archivo de configuración **Web.config** de la raíz predeterminada, o bien en un archivo de configuración de una aplicación web concreta.</span><span class="sxs-lookup"><span data-stu-id="b4be1-122">Specifically, the reference should be added under the **compilation**/**assemblies** section of the default root **Web.config** configuration file, or a specific Web application's configuration file.</span></span> <span data-ttu-id="b4be1-123">En el siguiente ejemplo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="b4be1-123">The following example demonstrates this.</span></span>  
  
```xml  
<configuration>  
   <system.web>  
      <compilation>  
         <assemblies>  
      <add assembly="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
         </assemblies>  
      </compilation>  
   </system.web>  
</configuration>  
```  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="b4be1-124"> [Elemento add aplicado a assemblies para compilation (Esquema de configuración de ASP.NET)](http://msdn.microsoft.com/en-us/602197e8-108d-4249-b752-ba2a318f75e4).</span><span class="sxs-lookup"><span data-stu-id="b4be1-124"> [add Element for assemblies for compilation (ASP.NET Settings Schema)](http://msdn.microsoft.com/en-us/602197e8-108d-4249-b752-ba2a318f75e4).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4be1-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4be1-125">See Also</span></span>  
 [<span data-ttu-id="b4be1-126">Niveles de confianza de ASP.NET y archivos de directivas</span><span class="sxs-lookup"><span data-stu-id="b4be1-126">ASP.NET Trust Levels and Policy Files</span></span>](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1)  
 [<span data-ttu-id="b4be1-127">securityPolicy Element (ASP.NET Settings Schema)</span><span class="sxs-lookup"><span data-stu-id="b4be1-127">securityPolicy Element (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/en-us/469d8d22-d263-46bb-8400-40d8d027faba)  
 [<span data-ttu-id="b4be1-128">Escalado de administración de transacciones</span><span class="sxs-lookup"><span data-stu-id="b4be1-128">Transaction Management Escalation</span></span>](../../../../docs/framework/data/transactions/transaction-management-escalation.md)
