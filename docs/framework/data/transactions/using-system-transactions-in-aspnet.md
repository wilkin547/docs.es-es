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
# <a name="using-systemtransactions-in-aspnet"></a>Usar System.Transactions en ASP.NET
Este tema describe cómo se puede utilizar <xref:System.Transactions> correctamente dentro de una aplicación ASP.NET.

## <a name="enable-distributedtransactionpermission-in-aspnet"></a>Habilitar DistributedTransactionPermission en ASP.NET
 <xref:System.Transactions>admite llamadores de confianza parcial y se marca con el `AllowPartiallyTrustedCallers` atributo (APTCA). Los niveles de confianza para <xref:System.Transactions> se definen en función de los tipos de recursos (por ejemplo, la memoria del sistema, los recursos compartidos de todo el proceso, los recursos de todo el sistema y otros recursos) que <xref:System.Transactions> expone y el nivel de confianza que debe ser necesario para tener acceso a esos recursos. En un entorno de confianza parcial, un ensamblado sin plena confianza puede usar solo las transacciones dentro del dominio de aplicación (en este caso, el único recurso que se protege es la memoria del sistema) a menos que se permita <xref:System.Transactions.DistributedTransactionPermission>.

 Se exige<xref:System.Transactions.DistributedTransactionPermission> cuando la administración de la transacción se escala para que el Coordinador de transacciones distribuidas de Microsoft (MSDTC) la administre. Este tipo de escenario usa recursos de todo el proceso y particularmente un recurso global, que es el espacio reservado en el registro de MSDTC. Un ejemplo de este uso es un front-end web con una base de datos o una aplicación que usa una base de datos como parte de los servicios que proporciona.

 ASP.NET tiene su propio conjunto de niveles de confianza y asocia un conjunto concreto de permisos con estos niveles de confianza a través de los archivos de directivas. Para obtener más información, consulte [niveles de confianza y archivos de directiva de ASP.net](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100)). Al instalar inicialmente el Windows SDK, ninguno de los archivos de directiva de ASP.NET predeterminados está asociado a <xref:System.Transactions.DistributedTransactionPermission> . Como tal, cuando su transacción en una aplicación ASP.NET realiza una escalada para ser administrada por MSDTC, se produce un error en la subida con <xref:System.Security.SecurityException> al exigir <xref:System.Transactions.DistributedTransactionPermission>. Debería permitir <xref:System.Transactions.DistributedTransactionPermission> en los mismos niveles de confianza predeterminados como aquéllos de <xref:System.Data.SqlClient.SqlClientPermission>para habilitar la subida de la transacción en un entorno confiable parcial de ASP.NET. Puede configurar su propio nivel de confianza personalizado y archivo de directivas para admitirlo o bien modificar los archivos de directivas predeterminados, **Web_hightrust.config** y **Web_mediumtrust.config**.

 Para modificar los archivos de directivas, agregue un `SecurityClass` elemento para `DistributedTransactionPermission` al `SecurityClasses` elemento bajo el `PolicyLevel` elemento y agregue un `IPermission` elemento correspondiente en ASP.net `NamedPermissionSet` para System. Transactions. Esto se muestra en el siguiente archivo de configuración.

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

 Para obtener más información sobre la Directiva de seguridad ASP.NET, vea [elemento securityPolicy (esquema de configuración de ASP.net)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100)).

## <a name="dynamic-compilation"></a>Compilación dinámica
 Si desea importar y utilizar <xref:System.Transactions> en una aplicación ASP.NET que está compilada dinámicamente en acceso, debería colocar una referencia al ensamblado <xref:System.Transactions> en el archivo de configuración. En concreto, la referencia debe agregarse en la `compilation/assemblies` sección del archivo de configuración **Web.config** raíz predeterminado o en el archivo de configuración de una aplicación web concreta. El ejemplo siguiente demuestra este patrón.

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

 Para obtener más información, vea [Add Element for assemblies for Compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100)).

## <a name="see-also"></a>Consulte también:

- [Niveles de confianza y archivos de directiva de ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))
- [Elemento securityPolicy (Esquema de configuración de ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))
- [Extensión de administración de transacción](transaction-management-escalation.md)
