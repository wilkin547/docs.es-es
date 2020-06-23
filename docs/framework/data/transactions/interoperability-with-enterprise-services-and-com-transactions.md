---
title: Interoperabilidad con Enterprise Services y transacciones de COM+
description: Comprenda la interoperabilidad con Enterprise Services y transacciones COM+ en .NET mediante el espacio de nombres System. Transactions.
ms.date: 03/30/2017
ms.assetid: d0fd0d26-fe86-443b-b208-4d57d39fa4aa
ms.openlocfilehash: ebd6166fbd99ef102cf10ba1bcef9e3eb8aaa5da
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141906"
---
# <a name="interoperability-with-enterprise-services-and-com-transactions"></a>Interoperabilidad con Enterprise Services y transacciones de COM+
El espacio de nombres <xref:System.Transactions> admite la interoperabilidad entre los objetos de transacción creados utilizando este espacio de nombres y las transacciones creadas a través de COM+.  
  
 Puede utilizar la enumeración <xref:System.Transactions.EnterpriseServicesInteropOption> al crear una nueva <xref:System.Transactions.TransactionScope> instancia para especificar el nivel de interoperabilidad con COM+.  
  
 De forma predeterminada, cuando el código de aplicación comprueba la <xref:System.Transactions.Transaction.Current%2A> propiedad estática, <xref:System.Transactions> intenta buscar una transacción que, de lo contrario, es actual o un <xref:System.Transactions.TransactionScope> objeto que determina que <xref:System.Transactions.Transaction.Current%2A> es **null**. Si no encuentra ninguno de estos, <xref:System.Transactions> consulta una transacción en el contexto de COM+. Tenga en cuenta que aunque <xref:System.Transactions> puede buscar una transacción del contexto de COM+, todavía favorece transacciones que son nativas a <xref:System.Transactions>.  
  
## <a name="interoperability-levels"></a>Niveles de la interoperabilidad  
 La enumeración <xref:System.Transactions.EnterpriseServicesInteropOption> define los niveles siguientes de interoperabilidad. <xref:System.Transactions.EnterpriseServicesInteropOption.None>, <xref:System.Transactions.EnterpriseServicesInteropOption.Full> y <xref:System.Transactions.EnterpriseServicesInteropOption.Automatic>.  
  
 La clase <xref:System.Transactions.TransactionScope> proporciona constructores que aceptan <xref:System.Transactions.EnterpriseServicesInteropOption> como un parámetro.  
  
 <xref:System.Transactions.EnterpriseServicesInteropOption.None>, como implica el nombre, implica que no hay ninguna interoperabilidad entre los <xref:System.EnterpriseServices> contextos y los ámbitos de transacción. Después de crear un objeto <xref:System.Transactions.TransactionScope> con <xref:System.Transactions.EnterpriseServicesInteropOption.None>, cualquier cambio a <xref:System.Transactions.Transaction.Current%2A> no se refleja en el contexto de COM+. De igual forma, cambia a la transacción en el contexto de COM+ no se refleja en <xref:System.Transactions.Transaction.Current%2A>. Este es el modo de funcionamiento más rápido para <xref:System.Transactions> porque no hay ninguna sincronización adicional necesaria. <xref:System.Transactions.EnterpriseServicesInteropOption.None> es el valor predeterminado usado por <xref:System.Transactions.TransactionScope> con todos los constructores que no aceptan <xref:System.Transactions.EnterpriseServicesInteropOption> como parámetro.  
  
 Si hace la necesidad para combinar las transacciones <xref:System.EnterpriseServices> con su transacción ambiente, necesita utilizar <xref:System.Transactions.EnterpriseServicesInteropOption.Full> o <xref:System.Transactions.EnterpriseServicesInteropOption.Automatic>. Ambos de estos valores confían en una característica llamada servicios sin componentes y por consiguiente debería estar ejecutándose en Windows XP Service Pack 2 o Windows Server 2003 al utilizarlos.  
  
 <xref:System.Transactions.EnterpriseServicesInteropOption.Full> especifica que las transacciones ambientes para <xref:System.Transactions> y <xref:System.EnterpriseServices> siempre son los mismos. Producir crear un nuevo <xref:System.EnterpriseServices> contexto transaccional y aplicar la transacción que es actual para que <xref:System.Transactions.TransactionScope> sea actual para ese contexto. Como a tal, la transacción en <xref:System.Transactions.Transaction.Current%2A> está completamente en sincronización con la transacción en <xref:System.EnterpriseServices.ContextUtil.Transaction%2A>. Este valor presenta una reducción del rendimiento porque quizá sea necesario crear nuevos contextos COM+ .  
  
 <xref:System.Transactions.EnterpriseServicesInteropOption.Automatic>especifica los siguientes requisitos:  
  
- Cuando se comprueba <xref:System.Transactions.Transaction.Current%2A>, <xref:System.Transactions> debería admitir las transacciones en el contexto de COM+ si detecta que se está ejecutando en un contexto distinto del contexto predeterminado. Observe que el contexto predeterminado no puede contener una transacción. Por consiguiente, en el contexto predeterminado, la transacción almacenada en el almacenamiento local de subprocesos utilizado por <xref:System.Transactions.EnterpriseServicesInteropOption.Automatic> se devuelve incluso con <xref:System.Transactions>, para <xref:System.Transactions.Transaction.Current%2A>.  
  
- Si se crea un nuevo objeto <xref:System.Transactions.TransactionScope> y la creación se produce en un contexto distinto del contexto predeterminado, la transacción que es actual para el objeto <xref:System.Transactions.TransactionScope> se debería reflejar en COM+. En este caso, <xref:System.Transactions.EnterpriseServicesInteropOption.Automatic> se comporta como <xref:System.Transactions.EnterpriseServicesInteropOption.Full> en eso crea un contexto de nuevo COM+.  
  
 Además cuando <xref:System.Transactions.Transaction.Current%2A> se establece en <xref:System.Transactions.EnterpriseServicesInteropOption.Full> y <xref:System.Transactions.EnterpriseServicesInteropOption.Automatic>, ambos de estos modos implican que no se puede establecer ese <xref:System.Transactions.Transaction.Current%2A> directamente.  Cualquier intento para establecer directamente <xref:System.Transactions.Transaction.Current%2A> otro distinto de crear resultados <xref:System.Transactions.TransactionScope> en un <xref:System.InvalidOperationException>. Nuevos ambientes de transacción han heredado el valor de enumeración <xref:System.Transactions.EnterpriseServicesInteropOption> que no especifica que valor hay que utilizar. Por ejemplo, si crea un nuevo objeto <xref:System.Transactions.TransactionScope> con <xref:System.Transactions.EnterpriseServicesInteropOption.Full>, y, a continuación, crea un segundo objeto <xref:System.Transactions.TransactionScope> pero no especifica un valor <xref:System.Transactions.EnterpriseServicesInteropOption>, el segundo objeto <xref:System.Transactions.TransactionScope> también tiene <xref:System.Transactions.EnterpriseServicesInteropOption.Full>.  
  
 En resumen, las reglas siguientes se aplican al crear un nuevo ámbito de la transacción:  
  
1. <xref:System.Transactions.Transaction.Current%2A>se comprueba para ver si hay una transacción. Comprueba los resultados en:  
  
    - Una comprobación para ver si hay un ámbito.  
  
    - Si hay un ámbito, el valor de la enumeración <xref:System.Transactions.EnterpriseServicesInteropOption> que se ha pasado cuando se ha creado el ámbito inicialmente, se comprueba.  
  
    - Si la enumeración <xref:System.Transactions.EnterpriseServicesInteropOption> está establecida en <xref:System.Transactions.EnterpriseServicesInteropOption.Automatic>, la transacción de COM+ (Transacción <xref:System.EnterpriseServices> ) tiene precedencia sobre la transacción <xref:System.Transactions> en almacenamiento local de subprocesos administrado.  
  
         Si el valor se ha establecido en <xref:System.Transactions.EnterpriseServicesInteropOption.None>, la transacción <xref:System.Transactions> toma precedentes en el almacenamiento local de subproceso.  
  
         Si el valor es <xref:System.Transactions.EnterpriseServicesInteropOption.Full>, hay solo una transacción y es una transacción de COM+.  
  
2. Se comprueba el valor de la enumeración <xref:System.Transactions.TransactionScopeOption> pasada por el constructor <xref:System.Transactions.TransactionScope>. Esto determina si se debe crear una nueva transacción.  
  
3. Si se va a crear una nueva transacción, los valores siguientes de resultado <xref:System.Transactions.EnterpriseServicesInteropOption> en:  
  
    - <xref:System.Transactions.EnterpriseServicesInteropOption.Full>: se crea una transacción asociada a un contexto de COM+.  
  
    - <xref:System.Transactions.EnterpriseServicesInteropOption.None>: <xref:System.Transactions> se crea una transacción.  
  
    - <xref:System.Transactions.EnterpriseServicesInteropOption.Automatic>: si hay un contexto de COM+, se crea una transacción y se adjunta al contexto.  
  
 La tabla siguiente muestra el contexto del Enterprise Services (ES) y un ámbito transaccional que requiere una transacción mediante la enumeración <xref:System.Transactions.EnterpriseServicesInteropOption>.  
  
|Contexto ES|None|Automático|Completo|  
|----------------|----------|---------------|----------|  
|Contexto predeterminado|Contexto predeterminado|Contexto predeterminado|Crear nuevo <br />contexto transaccional|  
|Contexto no predeterminado|Mantener el contexto de cliente|Crear el nuevo contexto transaccional|Crear el nuevo contexto transaccional|  
  
 La tabla siguiente muestra lo que es la transacción ambiente, dado un contexto <xref:System.EnterpriseServices> determinado y un ámbito transaccional que requiere una transacción mediante la enumeración <xref:System.Transactions.EnterpriseServicesInteropOption>.  
  
|Contexto ES|None|Automático|Completo|  
|----------------|----------|---------------|----------|  
|Contexto predeterminado|ST|ST|ES|  
|Contexto no predeterminado|ST|ES|ES|  
  
 En la tabla anterior:  
  
- ST quiere decir que <xref:System.Transactions> administra la transacción ambiente del ámbito, separada de la transacción de cualquier contexto <xref:System.EnterpriseServices> que puede estar presente.  
  
- ES quiere decir que la transacción ambiente del ámbito es la misma que la transacción del contexto <xref:System.EnterpriseServices>.
