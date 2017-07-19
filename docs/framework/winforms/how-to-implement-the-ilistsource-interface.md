---
title: "C&#243;mo: Implementar la interfaz IListSource | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "enlace de datos, implementar"
  - "IListSource (interfaz)"
ms.assetid: 63ce27aa-2e23-4fbd-8228-0c1726f6c421
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Implementar la interfaz IListSource
Implemente la interfaz <xref:System.ComponentModel.IListSource> para crear una clase enlazable que no implementa <xref:System.Collections.IList> sino proporciona una lista de otra ubicación en su lugar.  
  
## Ejemplo  
 En el ejemplo de código siguiente se muestra cómo implementar la interfaz <xref:System.ComponentModel.IListSource>.  Un componente llamado `EmployeeListSource` expone una <xref:System.Collections.IList> para el enlace de datos mediante la implementación del método <xref:System.ComponentModel.IListSource.GetList%2A>.  
  
 [!code-csharp[System.ComponentModel.IListSource#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/EmployeeListSource.cs#1)]
 [!code-vb[System.ComponentModel.IListSource#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/EmployeeListSource.vb#1)]  
  
 [!code-csharp[System.ComponentModel.IListSource#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/Employee.cs#10)]
 [!code-vb[System.ComponentModel.IListSource#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/Employee.vb#10)]  
  
 [!code-csharp[System.ComponentModel.IListSource#100](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/BusinessObjectBase.cs#100)]
 [!code-vb[System.ComponentModel.IListSource#100](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/BusinessObjectBase.vb#100)]  
  
 [!code-csharp[System.ComponentModel.IListSource#1000](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/Form1.cs#1000)]
 [!code-vb[System.ComponentModel.IListSource#1000](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/Form1.vb#1000)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System.Drawing y System.Windows.Forms.  
  
## Vea también  
 <xref:System.ComponentModel.IListSource>   
 <xref:System.ComponentModel.ITypedList>   
 <xref:System.ComponentModel.BindingList%601>   
 <xref:System.ComponentModel.IBindingList>   
 [Enlace de datos y formularios Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)