---
title: "Transacciones de flujo de trabajo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Transacciones de flujo de trabajo
[!INCLUDE[wf1](../../../includes/wf1-md.md)] proporciona el soporte técnico para participar en las transacciones del espacio de nombres <xref:System.Transactions> usando la actividad <xref:System.Activities.Statements.TransactionScope> para abarcar una unidad de trabajo con la que se haya realizado una transacción.Aunque la clase <xref:System.Transactions.TransactionScope?displayProperty=fullName> debe completarse explícitamente, la actividad <xref:System.Activities.Statements.TransactionScope?displayProperty=fullName> realiza una llamada implícita de finalización de la transacción cuando se haya completado correctamente.Las actividades que se contengan en <xref:System.Activities.Statements.TransactionScope.Body%2A> de la actividad <xref:System.Activities.Statements.TransactionScope> participan en la transacción.WF puede fluir las transacciones en un flujo de trabajo a través del uso de la actividad <xref:System.ServiceModel.Activities.TransactedReceiveScope>.Al igual que ocurre con la actividad <xref:System.Activities.Statements.TransactionScope>, cualquier actividad contenida en la propiedad <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> participa en la transacción.WF garantiza que las actividades dependientes de <xref:System.Transactions.Transaction.Current%2A?displayProperty=fullName> funcionan con <xref:System.Activities.Statements.TransactionScope> y <xref:System.ServiceModel.Activities.TransactedReceiveScope>.Si las actividades proporcionadas por el sistema no afrontan todos los requisitos, las actividades personalizadas se pueden compilar usando <xref:System.Activities.RuntimeTransactionHandle> para habilitar los escenarios de flujo avanzado y del control de transacciones.  
  
 En el ejemplo siguiente, tomado del ejemplo de [TransactionScope básico](../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md), se construye un flujo de trabajo que consta de una actividad <xref:System.Activities.Statements.Sequence> que contiene actividades secundarias incluida una actividad <xref:System.Activities.Statements.TransactionScope>.Las actividades <xref:System.Activities.Statements.TransactionScope.Body%2A> de <xref:System.Activities.Statements.TransactionScope> se ejecutan bajo la transacción inicializada por la actividad <xref:System.Activities.Statements.TransactionScope>.  
  
```csharp  
static Activity ScenarioOne()  
{  
    return new Sequence  
    {  
        Activities =  
        {  
            new WriteLine { Text = "    Begin workflow" },  
  
            new TransactionScope  
            {  
                Body = new Sequence  
                {  
                    Activities =   
                    {  
                        new WriteLine { Text = "    Begin TransactionScope" },  
  
                        new PrintTransactionId(),  
  
                        new TransactionScopeTest(),  
  
                        new WriteLine { Text = "    End TransactionScope" },  
                    },  
                },  
            },  
  
            new WriteLine { Text = "    End workflow" },  
        }  
    };  
}  
  
```  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] los ejemplos de [Transacciones](../../../docs/framework/windows-workflow-foundation/samples/basic-transactions.md) básicos y los ejemplos de [Transacciones](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) basados en escenarios.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)] cómo usar <xref:System.ServiceModel.Activities.TransactedReceiveScope>, vea [Flujo de las transacciones en los servicios de flujo de trabajo](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).  
  
## Vea también  
 <xref:System.Activities.Statements.TransactionScope>   
 <xref:System.Transactions.TransactionScope>   
 <xref:System.Transactions.Transaction.Current%2A?displayProperty=fullName>