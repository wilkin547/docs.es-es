---
title: Implementar una transacción implícita mediante el ámbito de la transacción
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d1706a-1e0c-4c85-9704-75c908372eb9
ms.openlocfilehash: 33b51cf26a35bbdda70582d86db6ac39c22597da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174399"
---
# <a name="implementing-an-implicit-transaction-using-transaction-scope"></a>Implementar una transacción implícita mediante el ámbito de la transacción
La clase <xref:System.Transactions.TransactionScope> proporciona una manera simple de marcar un bloque de código como participar en una transacción, sin exigirle que interactuara con la propia transacción. Un ámbito de la transacción puede seleccionar y administrar automáticamente la transacción ambiente. Debido a su facilidad de uso y eficacia, se recomienda que utilice la clase <xref:System.Transactions.TransactionScope> al desarrollar una aplicación de transacción.  
  
 Además, no necesita dar de alta explícitamente los recursos con la transacción. Cualquier administrador de recursos <xref:System.Transactions> (como SQL Server 2005) puede detectar la existencia de una transacción ambiente creada por el ámbito y automáticamente darse de alta.  
  
## <a name="creating-a-transaction-scope"></a>Crear un ámbito de la transacción  
 En el ejemplo siguiente se muestra un uso sencillo de la clase <xref:System.Transactions.TransactionScope>.  
  
 [!code-csharp[TransactionScope#1](../../../../samples/snippets/csharp/VS_Snippets_Remoting/TransactionScope/cs/ScopeWithSQL.cs#1)]
 [!code-vb[TransactionScope#1](../../../../samples/snippets/visualbasic/VS_Snippets_Remoting/TransactionScope/vb/ScopeWithSQL.vb#1)]  
  
 El ambiente de transacción ha comenzado una vez que se ha creado un nuevo objeto <xref:System.Transactions.TransactionScope> .  Como se muestra en el ejemplo de código, se `using` recomienda crear ámbitos con una instrucción. La `using` instrucción está disponible tanto en C- como `try`en Visual Basic, y funciona como un ... `finally` bloque para asegurarse de que el alcance se elimina correctamente.  
  
 Al crear una instancia de <xref:System.Transactions.TransactionScope>, el administrador de transacciones determina en qué transacción participar. Una vez determinado, el ámbito siempre participa en esa transacción. La decisión se basa en dos factores: si está presente una transacción de ambiente y el valor del parámetro `TransactionScopeOption` del constructor. La transacción ambiente es la transacción dentro de la que su código se ejecuta. Puede obtener una referencia a la transacción ambiente llamando a la propiedad estática <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> de la clase <xref:System.Transactions.Transaction>. Para obtener más información sobre cómo se usa este parámetro, vea la sección Administración del flujo de [transacciones mediante TransactionScopeOption](#ManageTxFlow) de este tema.  
  
## <a name="completing-a-transaction-scope"></a>Completar un ámbito de la transacción  
 Cuando la aplicación termina todo el trabajo que tiene que llevar a cabo en una transacción, debe llamar al método <xref:System.Transactions.TransactionScope.Complete%2A?displayProperty=nameWIthType> solo una vez para notificar al administrador de transacciones que la transacción se puede confirmar. Es muy buena práctica poner <xref:System.Transactions.TransactionScope.Complete%2A> la llamada como `using` la última instrucción en el bloque.  
  
 Si no se llama a este método, se anula la transacción, porque el administrador de transacciones interpreta esto como un error del sistema o equivalente a una excepción iniciada dentro del ámbito de la transacción. Sin embargo, llamar a este método no garantiza que se vaya a confirmar la transacción. Es solo una manera de informar al administrador de transacciones de su estado. Después de llamar a este método<xref:System.Transactions.TransactionScope.Complete%2A> ya no podrá obtener acceso a la transacción de ambiente mediante la propiedad <xref:System.Transactions.Transaction.Current%2A> y, si intenta hacerlo, se producirá una excepción.  
  
 Si <xref:System.Transactions.TransactionScope> el objeto creó la transacción inicialmente, el trabajo real de confirmar la `using` transacción por el administrador de transacciones se produce después de la última línea de código del bloque. Si no ha creado la transacción, se produce la confirmación cada vez que el propietario del objeto <xref:System.Transactions.CommittableTransaction.Commit%2A> llama al método <xref:System.Transactions.CommittableTransaction>. En ese momento, el administrador de transacciones llama a los administradores <xref:System.Transactions.TransactionScope.Complete%2A> de recursos y <xref:System.Transactions.TransactionScope> les informa para confirmar o revertir, en función de si se llamó al método en el objeto.  
  
 La `using` instrucción <xref:System.Transactions.TransactionScope.Dispose%2A> garantiza que <xref:System.Transactions.TransactionScope> se llama al método del objeto incluso si se produce una excepción. El método <xref:System.Transactions.TransactionScope.Dispose%2A> marca el fin del ámbito de la transacción. Las excepciones que se producen después de llamar a este método quizá no afecten a la transacción. Este método también restaura la transacción de ambiente a su estado previo.  
  
 Se inicia <xref:System.Transactions.TransactionAbortedException> si el ámbito crea la transacción, y ésta se anula. Se inicia <xref:System.Transactions.TransactionInDoubtException> si el administrador de transacciones no puede llegar a una decisión de la confirmación. No se produce ninguna excepción si se confirma la transacción.  
  
## <a name="rolling-back-a-transaction"></a>Revertir una transacción  
 Si desea revertir una transacción, no debería llamar al método <xref:System.Transactions.TransactionScope.Complete%2A> dentro del ámbito de la transacción. Por ejemplo, puede producir una excepción dentro del ámbito. Se deshará la transacción en la que participa.  
  
## <a name="managing-transaction-flow-using-transactionscopeoption"></a><a name="ManageTxFlow"></a>Administración del flujo de transacciones mediante TransactionScopeOption  
 El ámbito de la transacción puede estar anidado al llamar a un método que utiliza desde dentro <xref:System.Transactions.TransactionScope> un método que utiliza su propio ámbito, como es el caso con el método `RootMethod` en el ejemplo siguiente,  
  
```csharp  
void RootMethod()
{
    using(TransactionScope scope = new TransactionScope())
    {
        /* Perform transactional work here */
        SomeMethod();
        scope.Complete();
    }
}

void SomeMethod()
{
    using(TransactionScope scope = new TransactionScope())
    {
        /* Perform transactional work here */
        scope.Complete();
    }
}
```  
  
 El ámbito de la transacción de nivel superior se conoce como el ámbito de la raíz.  
  
 La clase <xref:System.Transactions.TransactionScope> proporciona varios constructores sobrecargados que aceptan una enumeración del tipo <xref:System.Transactions.TransactionScopeOption>, que define el comportamiento transaccional del ámbito.  
  
 Un objeto <xref:System.Transactions.TransactionScope> tiene tres opciones:  
  
- Unir la transacción ambiente o crear una nueva si no existe.  
  
- Ser un nuevo ámbito de la raíz, eso es, iniciar una nueva transacción y tener esa transacción siendo la nueva transacción ambiente dentro de su propio ámbito.  
  
- No tomar parte en absoluto en una transacción. Como resultado, no hay ninguna transacción ambiente.  
  
 Si se crean instancias del ámbito con <xref:System.Transactions.TransactionScopeOption.Required>, y una transacción ambiente está presente, el ámbito combina dicha transacción. Si, por otro lado, no hay ninguna transacción ambiente, a continuación, el ámbito crea una nueva transacción y se vuelve el ámbito de la raíz. Este es el valor predeterminado. Cuando se utiliza <xref:System.Transactions.TransactionScopeOption.Required>, el código dentro del ámbito no necesita comportarse de manera diferente si es la raíz o simplemente uniendo la transacción ambiente. Debería funcionar idénticamente en ambos casos.  
  
 Si se crean instancias del ámbito con <xref:System.Transactions.TransactionScopeOption.RequiresNew>, siempre es el ámbito de la raíz. Inicia una nueva transacción y su transacción se vuelve la nueva transacción ambiente dentro del ámbito.  
  
 Si se crea del ámbito instancias con <xref:System.Transactions.TransactionScopeOption.Suppress>, nunca toma la parte en una transacción, sin tener en cuenta si una transacción ambiente está presente. Un ámbito que se crea `null` con este valor siempre tiene como transacción ambiente.  
  
 Las opciones anteriores se resumen en la tabla siguiente.  
  
|TransactionScopeOption|Transacción ambiente|El ámbito toma parte.|  
|----------------------------|-------------------------|-----------------------------|  
|Obligatorio|Sin |Nueva transacción (será la raíz)|  
|Se requiere nueva|Sin |Nueva transacción (será la raíz)|  
|Suprimir|Sin |Sin transacción|  
|Obligatorio|Sí|Transacción ambiente|  
|Se requiere nueva|Sí|Nueva transacción (será la raíz)|  
|Suprimir|Sí|Sin transacción|  
  
 Cuando un objeto <xref:System.Transactions.TransactionScope> une una transacción ambiente existente, al eliminar el objeto de ámbito, no se puede finalizar la transacción, a menos que el ámbito anule la transacción. Si un ámbito de la raíz creara la transacción ambiente, solo cuando el ámbito de la raíz se elimina, se llama <xref:System.Transactions.CommittableTransaction.Commit%2A> en la transacción. Si se crea la transacción manualmente, la transacción finaliza cuando se anula o cuando su creador la confirma.  
  
 El ejemplo siguiente muestra un objeto <xref:System.Transactions.TransactionScope> que crea tres objetos de ámbito anidados, cada uno con instancias con un valor <xref:System.Transactions.TransactionScopeOption> diferente.  
  
```csharp  
using(TransactionScope scope1 = new TransactionScope())
//Default is Required
{
    using(TransactionScope scope2 = new TransactionScope(TransactionScopeOption.Required))
    {
        //...
    }

    using(TransactionScope scope3 = new TransactionScope(TransactionScopeOption.RequiresNew))
    {
        //...  
    }
  
    using(TransactionScope scope4 = new TransactionScope(TransactionScopeOption.Suppress))
    {
        //...  
    }
}
```  
  
 El ejemplo muestra un bloque de código sin cualquier transacción ambiente que crea un nuevo ámbito (`scope1`) con <xref:System.Transactions.TransactionScopeOption.Required>. El ámbito `scope1` es un ámbito raíz porque cuando crea una nueva transacción (la transacción A) y hace que la transacción A sea transacción ambiente. `Scope1`a continuación, crea tres objetos más, cada uno con un valor diferente. <xref:System.Transactions.TransactionScopeOption> Por ejemplo, `scope2` se crea con <xref:System.Transactions.TransactionScopeOption.Required>y hay subsecuentemente una transacción ambiente, que se une la primera transacción creada por `scope1`. Observe que `scope3` es el ámbito de la raíz de una nueva transacción, y `scope4` no tiene ninguna transacción ambiente.  
  
 Aunque el valor predeterminado y más comúnmente utilizado de <xref:System.Transactions.TransactionScopeOption> es <xref:System.Transactions.TransactionScopeOption.Required>, cada uno de los otros valores tiene su propósito único.  

### <a name="non-transactional-code-inside-a-transaction-scope"></a>Código no transaccional dentro de un ámbito de transacción

 <xref:System.Transactions.TransactionScopeOption.Suppress>es útil cuando desea conservar las operaciones realizadas por la sección de código y no desea anular la transacción ambiente si se produce un error en las operaciones. Por ejemplo, al desear realizar un registro u operaciones de la auditoría, o al desear publicar los eventos a los suscriptores sin tener en cuenta si su transacción ambiente se confirma o sufre interrupciones. Este valor le permite tener una sección de código no transaccional dentro de un ámbito de la transacción, como se muestra en el ejemplo siguiente.  
  
```csharp  
using(TransactionScope scope1 = new TransactionScope())
{
    try
    {
        //Start of non-transactional section
        using(TransactionScope scope2 = new
            TransactionScope(TransactionScopeOption.Suppress))  
        {  
            //Do non-transactional work here  
        }  
        //Restores ambient transaction here
   }
   catch {}  
   //Rest of scope1
}
```  
  
### <a name="voting-inside-a-nested-scope"></a>Votar dentro de un ámbito anidado  
 Aunque un ámbito anidado puede unir la transacción ambiente del ámbito de la raíz, llamar <xref:System.Transactions.TransactionScope.Complete%2A> en el ámbito anidado no tiene ningún efecto en el ámbito de la raíz. Sólo si todos los ámbitos del ámbito de la raíz, hasta el último del ámbito anidado, votan para confirmar la transacción, la transacción se confirmará. Si no se llama a <xref:System.Transactions.TransactionScope.Complete%2A> en un ámbito anidado afectará al ámbito de la raíz ya que la transacción ambiente se anulará inmediatamente.  
  
## <a name="setting-the-transactionscope-timeout"></a>Establecer el tiempo de espera de TransactionScope  
 Algunos de los constructores sobrecargados de <xref:System.Transactions.TransactionScope> aceptan un valor de tipo <xref:System.TimeSpan>, que se utiliza para controlar el tiempo de espera de la transacción. Un conjunto de tiempos de espera establecidos a cero significa un tiempo de espera infinito. El tiempo de espera infinito es principalmente útil para depurar, al desear aislar un problema en su lógica comercial caminando a través de su código, y no desear la transacción que depura el tiempo de espera mientras intenta buscar el problema. Sea sumamente cuidadoso utilizando el valor de tiempo de espera infinito en todos los otros casos, porque invalida las medidas de seguridad contra los interbloqueos de la transacción.  
  
 Se establece normalmente el tiempo de espera <xref:System.Transactions.TransactionScope> en los valores distintos del valor predeterminado en dos casos. El primero durante el desarrollo, al desear probar la manera en que su aplicación administra las transacciones anuladas. Estableciendo el tiempo de espera en un valor pequeño (como un milisegundo), hace que su transacción produzca un error y observa así su código de control de errores. El segundo caso en el que establece el valor para ser menor que el tiempo de espera predeterminado es al creer que el ámbito está implicado en la contención del recurso, produciendo los interbloqueos. En ese caso, desea anular lo antes posible la transacción y no esperar para que el tiempo de espera predeterminado expire.  
  
 Cuando un ámbito combina una transacción ambiente pero especifica un tiempo de espera menor que el de la transacción ambiente, el nuevo tiempo de espera más corto se exige en el objeto <xref:System.Transactions.TransactionScope> y el ámbito debe finalizar dentro de la hora anidada especificada o se anula la transacción automáticamente. Si el tiempo de espera del ámbito anidado es más que eso de la transacción ambiente, no tiene ningún efecto.  
  
## <a name="setting-the-transactionscope-isolation-level"></a>Establecer el nivel de aislamiento de TransactionScope  
 Algunos de los constructores sobrecargados de <xref:System.Transactions.TransactionScope> aceptan una estructura de tipo <xref:System.Transactions.TransactionOptions> para especificar un nivel de aislamiento, además de un valor de tiempo de espera. De forma predeterminada, la transacción se ejecuta con nivel de aislamiento establecido en <xref:System.Transactions.IsolationLevel.Serializable>. La selección de un nivel de aislamiento distinto de <xref:System.Transactions.IsolationLevel.Serializable> se utiliza normalmente para los sistemas de lectura-intensivos. Esto requiere un sólido entendimiento de teoría del procesamiento de transacciones y las semántica de la propia transacción, los problemas de simultaneidad implicados y las consecuencias para la coherencia del sistema.  
  
 Además, no todos los administradores de recursos admiten todos los niveles de aislamiento y pueden elegir tomar parte en la transacción en un nivel más alto que el que se configuró.  
  
 Cada nivel de aislamiento además de <xref:System.Transactions.IsolationLevel.Serializable> es susceptible a la inconsistencia que es el resultado de otras transacciones que tienen acceso a la misma información. La diferencia entre los niveles de aislamiento diferentes es la manera en que se utilizan los bloqueos de la lectura y escritura. Se puede contener un bloqueo solo cuando la transacción tiene acceso a los datos en el administrador de recursos, o se puede contener hasta que la transacción se confirme o anule. Lo primero es mejor para el rendimiento, lo último para la coherencia. Los dos tipos de bloqueos y los dos tipos de operaciones (lectura/escritura) proporcionan cuatro niveles de aislamiento básicos. Consulte <xref:System.Transactions.IsolationLevel> para obtener más información.  
  
 Al utilizar los objetos <xref:System.Transactions.TransactionScope> anidados, todos los ámbitos anidados se deben configurar para utilizar exactamente el mismo nivel de aislamiento si desean unir la transacción ambiente. Si un objeto <xref:System.Transactions.TransactionScope> anidado intenta unir la transacción ambiente todavía especifica un nivel de aislamiento diferente, se inicia <xref:System.ArgumentException>.  
  
## <a name="interop-with-com"></a>Interoperabilidad con COM+  
 Al crear que una nueva instancia <xref:System.Transactions.TransactionScope>, se puede utilizar la enumeración <xref:System.Transactions.EnterpriseServicesInteropOption> en uno de los constructores para especificar cómo interactuar con COM+. Para obtener más información al respecto, vea [Interoperabilidad con Enterprise Services y Transacciones COM+.](interoperability-with-enterprise-services-and-com-transactions.md)  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Transactions.Transaction.Clone%2A>
- <xref:System.Transactions.TransactionScope>
