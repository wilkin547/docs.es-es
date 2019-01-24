---
title: Usar System.Transactions en ASP.NET
ms.date: 03/30/2017
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
ms.openlocfilehash: 7c83532de42faff06594305b01137fd8fd63674e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711832"
---
# <a name="using-systemtransactions-in-aspnet"></a>Usar System.Transactions en ASP.NET
En este tema se describe cómo se puede usar <xref:System.Transactions> correctamente en una aplicación [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] .  
  
## <a name="enable-distributedtransactionpermission-in-aspnet"></a>Habilitar DistributedTransactionPermission en ASP.NET  
 <xref:System.Transactions> admite los llamadores de confianza parcial y se marca con el atributo **AllowPartiallyTrustedCallers** (APTCA). Los niveles de confianza para <xref:System.Transactions> se definen dependiendo de los tipos de recursos, por ejemplo, la memoria del sistema, los recursos de todo el proceso compartido, los recursos para todo el sistema y otros recursos. <xref:System.Transactions> expone dichos tipos de recursos y el nivel de confianza que se debería exigir para tener acceso a ellos. En un entorno de confianza parcial, un ensamblado sin plena confianza puede usar solo las transacciones dentro del dominio de aplicación (en este caso, el único recurso que se protege es la memoria del sistema) a menos que se permita <xref:System.Transactions.DistributedTransactionPermission>.  
  
 Se exige<xref:System.Transactions.DistributedTransactionPermission> cuando la administración de la transacción se escala para que el Coordinador de transacciones distribuidas de Microsoft (MSDTC) la administre. Este tipo de escenario utiliza todos los recursos proceso  y particularmente un recurso global, que es el espacio reservado en el registro de MSDTC. Un ejemplo de este uso es un front-end web con una base de datos o una aplicación que usa una base de datos como parte de los servicios que proporciona.  
  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] tiene su propio conjunto de niveles de confianza y asocia un conjunto concreto de permisos con estos niveles de confianza a través de los archivos de directivas. Para obtener más información, consulte [niveles de confianza de ASP.NET y los archivos de directiva](https://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1). Cuando instala inicialmente Windows SDK, ninguno de los archivos de directivas [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] predeterminados está asociado con <xref:System.Transactions.DistributedTransactionPermission>. Como tal, cuando la transacción en una aplicación [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] se escala para que el MSDTC la administre, se produce un error en la extensión con <xref:System.Security.SecurityException> al exigir <xref:System.Transactions.DistributedTransactionPermission>. Para habilitar la extensión de transacciones en un entorno de confianza parcial de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , debe conceder <xref:System.Transactions.DistributedTransactionPermission> en los mismos niveles de confianza predeterminados como los de <xref:System.Data.SqlClient.SqlClientPermission>. Puede configurar su propio nivel de confianza personalizado y archivo de directivas para admitirlo o bien modificar los archivos de directivas predeterminados, **Web_hightrust.config** y **Web_mediumtrust.config**.  
  
 Para modificar los archivos de directivas, agregue un **SecurityClass** (elemento) para **DistributedTransactionPermission** a la **SecurityClasses** elemento bajo el  **PolicyLevel** elemento y agregue correspondiente **IPermission** elemento bajo el [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** para System.Transactions. Esto se muestra en el siguiente archivo de configuración.  
  
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
  
 Para obtener más información acerca de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] directiva de seguridad, consulte [securityPolicy Element (ASP.NET Settings Schema)](https://msdn.microsoft.com/library/469d8d22-d263-46bb-8400-40d8d027faba).  
  
## <a name="dynamic-compilation"></a>Compilación dinámica  
 Si quiere importar y usar <xref:System.Transactions> en una aplicación [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] que está compilada dinámicamente en acceso, debe colocar una referencia al ensamblado <xref:System.Transactions> en el archivo de configuración. Específicamente, la referencia debe agregarse en la sección **compilation**/**assemblies** del archivo de configuración **Web.config** de la raíz predeterminada, o bien en un archivo de configuración de una aplicación web concreta. En el siguiente ejemplo se muestra cómo hacerlo.  
  
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
  
 Para obtener más información, consulte [elemento add aplicado a assemblies para compilation (esquema de configuración de ASP.NET)](https://msdn.microsoft.com/library/602197e8-108d-4249-b752-ba2a318f75e4).  
  
## <a name="see-also"></a>Vea también
- [Niveles de confianza de ASP.NET y los archivos de directivas](https://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1)
- [Elemento securityPolicy (esquema de configuración de ASP.NET)](https://msdn.microsoft.com/library/469d8d22-d263-46bb-8400-40d8d027faba)
- [Escalado de administración de transacciones](../../../../docs/framework/data/transactions/transaction-management-escalation.md)
