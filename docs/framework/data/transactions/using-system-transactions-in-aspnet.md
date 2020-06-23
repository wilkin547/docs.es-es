---
title: Usar System.Transactions en ASP.NET
description: Usar System. Transactions dentro de una aplicación ASP.NET. Habilitar los permisos de transacciones distribuidas y trabajar con la compilación dinámica.
ms.date: 03/30/2017
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
ms.openlocfilehash: 48907faf99953e34d045a1e0d79eed8a788187b5
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141649"
---
# <a name="using-systemtransactions-in-aspnet"></a><span data-ttu-id="30704-104">Usar System.Transactions en ASP.NET</span><span class="sxs-lookup"><span data-stu-id="30704-104">Using System.Transactions in ASP.NET</span></span>
<span data-ttu-id="30704-105">Este tema describe cómo se puede utilizar <xref:System.Transactions> correctamente dentro de una aplicación ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="30704-105">This topic describes how you can successfully use <xref:System.Transactions> inside an ASP.NET application.</span></span>

## <a name="enable-distributedtransactionpermission-in-aspnet"></a><span data-ttu-id="30704-106">Habilitar DistributedTransactionPermission en ASP.NET</span><span class="sxs-lookup"><span data-stu-id="30704-106">Enable DistributedTransactionPermission in ASP.NET</span></span>
 <span data-ttu-id="30704-107"><xref:System.Transactions>admite llamadores de confianza parcial y se marca con el `AllowPartiallyTrustedCallers` atributo (APTCA).</span><span class="sxs-lookup"><span data-stu-id="30704-107"><xref:System.Transactions> supports partially trusted callers and is marked with the `AllowPartiallyTrustedCallers` attribute (APTCA).</span></span> <span data-ttu-id="30704-108">Los niveles de confianza para <xref:System.Transactions> se definen en función de los tipos de recursos (por ejemplo, la memoria del sistema, los recursos compartidos de todo el proceso, los recursos de todo el sistema y otros recursos) que <xref:System.Transactions> expone y el nivel de confianza que debe ser necesario para tener acceso a esos recursos.</span><span class="sxs-lookup"><span data-stu-id="30704-108">The trust levels for <xref:System.Transactions> are defined based on the types of resources (for example, system memory, shared process-wide resources, system-wide resources, and other resources) that <xref:System.Transactions> exposes and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="30704-109">En un entorno de confianza parcial, un ensamblado sin plena confianza puede usar solo las transacciones dentro del dominio de aplicación (en este caso, el único recurso que se protege es la memoria del sistema) a menos que se permita <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="30704-109">In a partial-trust environment, a non-full trust assembly can only use transactions within the Application Domain (in this case, the only resource being protected is system memory), unless it is granted the <xref:System.Transactions.DistributedTransactionPermission>.</span></span>

 <span data-ttu-id="30704-110">Se exige<xref:System.Transactions.DistributedTransactionPermission> cuando la administración de la transacción se escala para que el Coordinador de transacciones distribuidas de Microsoft (MSDTC) la administre.</span><span class="sxs-lookup"><span data-stu-id="30704-110"><xref:System.Transactions.DistributedTransactionPermission> is demanded whenever transaction management is escalated to be managed by the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span> <span data-ttu-id="30704-111">Este tipo de escenario usa recursos de todo el proceso y particularmente un recurso global, que es el espacio reservado en el registro de MSDTC.</span><span class="sxs-lookup"><span data-stu-id="30704-111">This kind of scenario utilizes process-wide resources and particularly a global resource, which is the reserved space in the MSDTC log.</span></span> <span data-ttu-id="30704-112">Un ejemplo de este uso es un front-end web con una base de datos o una aplicación que usa una base de datos como parte de los servicios que proporciona.</span><span class="sxs-lookup"><span data-stu-id="30704-112">An example of this usage is a Web front-end to a database or an application that uses a database as part of the services it provides.</span></span>

 <span data-ttu-id="30704-113">ASP.NET tiene su propio conjunto de niveles de confianza y asocia un conjunto concreto de permisos con estos niveles de confianza a través de los archivos de directivas.</span><span class="sxs-lookup"><span data-stu-id="30704-113">ASP.NET has its own set of trust levels and associates a specific set of permissions with these trust levels through policy files.</span></span> <span data-ttu-id="30704-114">Para obtener más información, consulte [niveles de confianza y archivos de directiva de ASP.net](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="30704-114">For more information, see [ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100)).</span></span> <span data-ttu-id="30704-115">Al instalar inicialmente el Windows SDK, ninguno de los archivos de directiva de ASP.NET predeterminados está asociado a <xref:System.Transactions.DistributedTransactionPermission> .</span><span class="sxs-lookup"><span data-stu-id="30704-115">When you initially install the Windows SDK, none of the default ASP.NET policy files are associated with the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="30704-116">Como tal, cuando su transacción en una aplicación ASP.NET realiza una escalada para ser administrada por MSDTC, se produce un error en la subida con <xref:System.Security.SecurityException> al exigir <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="30704-116">As such, when your transaction in an ASP.NET application is escalated to be managed by the MSDTC, the escalation fails with a <xref:System.Security.SecurityException> upon demanding the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="30704-117">Debería permitir <xref:System.Transactions.DistributedTransactionPermission> en los mismos niveles de confianza predeterminados como aquéllos de <xref:System.Data.SqlClient.SqlClientPermission>para habilitar la subida de la transacción en un entorno confiable parcial de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="30704-117">To enable transaction escalation in an ASP.NET partial trust environment, you should grant the <xref:System.Transactions.DistributedTransactionPermission> in the same default trust levels as those of <xref:System.Data.SqlClient.SqlClientPermission>.</span></span> <span data-ttu-id="30704-118">Puede configurar su propio nivel de confianza personalizado y archivo de directivas para admitirlo o bien modificar los archivos de directivas predeterminados, **Web_hightrust.config** y **Web_mediumtrust.config**.</span><span class="sxs-lookup"><span data-stu-id="30704-118">You can either configure your own custom trust level and policy file to support this, or you can modify the default policy files, which are **Web_hightrust.config** and **Web_mediumtrust.config**.</span></span>

 <span data-ttu-id="30704-119">Para modificar los archivos de directivas, agregue un `SecurityClass` elemento para `DistributedTransactionPermission` al `SecurityClasses` elemento bajo el `PolicyLevel` elemento y agregue un `IPermission` elemento correspondiente en ASP.net `NamedPermissionSet` para System. Transactions.</span><span class="sxs-lookup"><span data-stu-id="30704-119">To modify the policy files, add a `SecurityClass` element for `DistributedTransactionPermission` to the `SecurityClasses` element under the `PolicyLevel` element and add a corresponding `IPermission` element under the ASP.NET `NamedPermissionSet` for System.Transactions.</span></span> <span data-ttu-id="30704-120">Esto se muestra en el siguiente archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="30704-120">The following configuration file demonstrates this.</span></span>

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

 <span data-ttu-id="30704-121">Para obtener más información sobre la Directiva de seguridad ASP.NET, vea [elemento securityPolicy (esquema de configuración de ASP.net)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="30704-121">For more information about ASP.NET security policy, see [securityPolicy Element (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100)).</span></span>

## <a name="dynamic-compilation"></a><span data-ttu-id="30704-122">Compilación dinámica</span><span class="sxs-lookup"><span data-stu-id="30704-122">Dynamic Compilation</span></span>
 <span data-ttu-id="30704-123">Si desea importar y utilizar <xref:System.Transactions> en una aplicación ASP.NET que está compilada dinámicamente en acceso, debería colocar una referencia al ensamblado <xref:System.Transactions> en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="30704-123">If you want to import and use <xref:System.Transactions> in an ASP.NET application that is dynamically compiled on access, you should place a reference to the <xref:System.Transactions> assembly in the configuration file.</span></span> <span data-ttu-id="30704-124">En concreto, la referencia debe agregarse en la `compilation/assemblies` sección del archivo de configuración **Web.config** raíz predeterminado o en el archivo de configuración de una aplicación web concreta.</span><span class="sxs-lookup"><span data-stu-id="30704-124">Specifically, the reference should be added under the `compilation/assemblies` section of the default root **Web.config** configuration file, or a specific Web application's configuration file.</span></span> <span data-ttu-id="30704-125">El ejemplo siguiente demuestra este patrón.</span><span class="sxs-lookup"><span data-stu-id="30704-125">The following example demonstrates this.</span></span>

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

 <span data-ttu-id="30704-126">Para obtener más información, vea [Add Element for assemblies for Compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="30704-126">For more information, see [add Element for assemblies for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100)).</span></span>

## <a name="see-also"></a><span data-ttu-id="30704-127">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="30704-127">See also</span></span>

- <span data-ttu-id="30704-128">[Niveles de confianza y archivos de directiva de ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="30704-128">[ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))</span></span>
- <span data-ttu-id="30704-129">[Elemento securityPolicy (Esquema de configuración de ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="30704-129">[securityPolicy Element (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))</span></span>
- [<span data-ttu-id="30704-130">Extensión de administración de transacción</span><span class="sxs-lookup"><span data-stu-id="30704-130">Transaction Management Escalation</span></span>](transaction-management-escalation.md)
