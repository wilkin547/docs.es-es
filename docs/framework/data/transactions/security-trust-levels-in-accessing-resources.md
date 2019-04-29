---
title: Niveles de confianza de seguridad para acceder a los recursos
ms.date: 03/30/2017
ms.assetid: fb5be924-317d-4d69-b33a-3d18ecfb9d6e
ms.openlocfilehash: 8e7d632c361ea73cb65668e43506d9e1128d31ca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793606"
---
# <a name="security-trust-levels-in-accessing-resources"></a>Niveles de confianza de seguridad para acceder a los recursos
En este tema se discute cómo el acceso está restringido en los tipos de recursos que <xref:System.Transactions> expone.  
  
 Hay tres niveles principales de confianza para <xref:System.Transactions>. Los niveles de confianza se definen dependiendo de los tipos de recursos que <xref:System.Transactions> expone y el nivel de confianza que se debería exigir para tener acceso a esos recursos. Los recursos a los que <xref:System.Transactions> proporciona acceso, son la memoria del sistema, recursos amplios de proceso compartido y los recursos para todo el sistema. Los niveles son los siguientes:  
  
- **AllowPartiallyTrustedCallers** (APTCA) para aplicaciones que usan las transacciones dentro de un dominio de aplicación único.  
  
- **DistributedTransactionPermission** (DTP) para aplicaciones que usan transacciones distribuidas.  
  
- Plena confianza para los recursos duraderos, aplicaciones de gestión de la configuración y las aplicaciones interoperativas heredadas.  
  
> [!NOTE]
>  No se debería llamar a cualquiera de las interfaces de inscripción con contextos suplantados.  
  
## <a name="trust-levels"></a>Niveles de confianza  
  
### <a name="aptca-partial-trust"></a>APTCA (confianza parcial)  
 El <xref:System.Transactions> ensamblado puede llamarse mediante código de confianza parcial porque se ha marcado con el **AllowPartiallyTrustedCallers** atributo (APTCA). Este atributo básicamente quita implícito <xref:System.Security.Permissions.SecurityAction.LinkDemand> para el **FullTrust** conjunto de permisos que se lo contrario, colocan automáticamente en cada método público accesible de cada tipo. Sin embargo, algunos tipos y miembros siguen necesitando permisos más firmes.  
  
 El atributo APTCA permite a las aplicaciones utilizar las transacciones en confianza parcial dentro de un dominio de aplicación único. Esto habilita las transacciones no escalonadas y las inscripciones volátiles que se pueden utilizar para el control de errores. Un ejemplo de esto es una tabla hash llevada a cabo y una aplicación que lo utiliza. Los datos se pueden agregar a y quitar de la tabla hash bajo una transacción única. Si se deshace la transacción después, se pueden deshacer todos los cambios realizados a la tabla hash bajo esa transacción.  
  
### <a name="distributedtransactionpermission-dtp"></a>DistributedTransactionPermission (DTP)  
 Cuando se realiza una escalada una transacción <xref:System.Transactions> para ser administrada por MSDTC, <xref:System.Transactions> exige (DTP) <xref:System.Transactions.DistributedTransactionPermission> para crear la transacción distribuida. Esto significa que el código que produce la transacción que ha de realizar una escalada (como a través de serialización o las inscripciones adicionales duraderas) necesitaría ser concedido DTP. El código que originalmente creó la transacción <xref:System.Transactions> necesariamente no necesita poseer este permiso.  
  
### <a name="fulltrust-link-demands"></a>Peticiones de vínculo de FullTrust  
 Se piensa que este nivel de permisos restringe aplicaciones que están escribiendo en los recursos duraderos. En el error, la aplicación necesita poder recuperarse con el administrador de transacciones para determinar el último resultado de la transacción, para que pueda actualizar los datos permanentes. Este tipo de aplicación es conocido como un administrador de origen duradero. Un ejemplo clásico de este tipo de aplicación es SQL.  
  
 Para habilitar la recuperación, este tipo de aplicación tiene la capacidad de utilizar permanentemente los recursos del sistema. Esto sucede porque el administrador de transacciones recuperable debe recordar transacciones que se han confirmado hasta que pueda confirmar que todos los administradores de recursos duraderos que están participando en la transacción han recibido el resultado. Por consiguiente, este tipo de aplicación requiere la plena confianza y no se ejecuta a menos que se haya permitido ese nivel de confianza.  
  
 Para obtener más información sobre inscripciones duraderas y recuperación, consulte el [dar de alta recursos como participantes en una transacción](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) y [realizar recuperación](../../../../docs/framework/data/transactions/performing-recovery.md) temas.  
  
 También exigen a las aplicaciones que realizan el trabajo de la interoperabilidad heredado con COM+ que tengan la plena confianza.  
  
 La siguiente es una lista de tipos y miembros que no son invocables por parcialmente el código de confianza ya que se decoran con el **FullTrust** atributo de seguridad declarativa:  
  
 `PermissionSetAttribute(SecurityAction.LinkDemand, Name := "FullTrust")`  
  
- <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType>  
  
- <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A>  
  
- <xref:System.Transactions.TransactionInterop>  
  
- <xref:System.Transactions.TransactionManager.DistributedTransactionStarted>  
  
- <xref:System.Transactions.HostCurrentTransactionCallback>  
  
- <xref:System.Transactions.TransactionManager.Reenlist%2A>  
  
- <xref:System.Transactions.TransactionManager.RecoveryComplete%2A>  
  
- <xref:System.Transactions.TransactionScope.%23ctor%28System.Transactions.TransactionScopeOption%2CSystem.Transactions.TransactionOptions%2CSystem.Transactions.EnterpriseServicesInteropOption%29>  
  
 Solo el llamador inmediato tiene que poseer el **FullTrust** conjunto de permisos para usar los tipos anteriores o métodos.
