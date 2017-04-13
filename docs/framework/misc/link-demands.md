---
title: "Link Demands | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "security [.NET Framework], demands"
  - "demanded permissions"
  - "permissions [.NET Framework], demands"
  - "granting permissions, demands"
  - "code access security, demands"
  - "user demands for permission"
  - "caller security checks"
  - "link demands"
ms.assetid: a33fd5f9-2de9-4653-a4f0-d9df25082c4d
caps.latest.revision: 18
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# Link Demands
Una petición de vínculo hace que se produzca una comprobación de seguridad durante la compilación Just\-In\-Time y comprueba solo el ensamblado de llamada inmediato del código.  La vinculación se produce cuando el código se enlaza a una referencia de tipo, incluidas las referencias del puntero de función y las llamadas a métodos.  Si el ensamblado de llamada no tiene permisos suficientes para vincularse al código, no se permitirá el vínculo y se producirá una excepción en tiempo de ejecución cuando se cargue y ejecute el código.  Las peticiones de vínculo pueden reemplazarse en las clases que heredan de su código.  
  
 Tenga en cuenta que no se efectúa ningún recorrido de pila completo con este tipo de petición y que el código sigue siendo vulnerable a ataques.  Por ejemplo, si una petición de vínculo protege un método del ensamblado A, se evalúa a un llamador directo del ensamblado B según los permisos del ensamblado B.  Sin embargo, la petición de vínculo no evaluará ningún método del ensamblado C si llama indirectamente al método del ensamblado A con el método del ensamblado B.  La petición de vínculo solo especifica que los llamadores directos de permisos del ensamblado de llamada inmediato deben estar vinculados al código.  No especifica los permisos que deben tener todos los llamadores para ejecutar el código.  
  
 Los modificadores de recorrido de pila <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> y <xref:System.Security.CodeAccessPermission.PermitOnly%2A> no afectan a la evaluación de las peticiones de vínculo.  Dado que las peticiones de vínculo no efectúan ningún recorrido de pila, los modificadores de recorrido de pila no tienen ningún efecto sobre las peticiones de vínculo.  
  
 Si se accede a un método protegido por una petición de vínculo a través de [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md), habrá una petición de vínculo que comprobará el llamador inmediato del código al que se ha accedido a través de reflexión.  Esto es válido tanto para la detección de métodos como para la invocación de métodos efectuados por reflexión.  Por ejemplo, supongamos que el código usa la reflexión para devolver un objeto <xref:System.Reflection.MethodInfo> que representa un método protegido por una petición de vínculo y, luego, pasa el objeto **MethodInfo** a otro código que usa dicho objeto para invocar el método original.  En este caso, la comprobación de la petición de vínculo tiene lugar dos veces: una vez para el código que devuelve el objeto **MethodInfo** y otra para el código que lo invoca.  
  
> [!NOTE]
>  Una petición de vínculo efectuada en un constructor de clases estáticas no protege el constructor, puesto que el sistema llama a los constructores estáticos, fuera de la ruta de acceso de ejecución del código de la aplicación.  Como resultado, al aplicar una petición de vínculo a toda una clase, no puede proteger el acceso a un constructor estático, aunque proteja el resto de la clase.  
  
 El siguiente fragmento de código especifica de manera declarativa que cualquier código vinculado al método `ReadData` debe tener el permiso `CustomPermission`.  Este permiso es un permiso personalizado hipotético y no existe en .NET Framework.  La petición se efectúa pasando una marca **SecurityAction.LinkDemand** a `CustomPermissionAttribute`.  
  
```vb  
<CustomPermissionAttribute(SecurityAction.LinkDemand)> _  
Public Shared Function ReadData() As String  
    ' Access a custom resource.  
End Function    
```  
  
```csharp  
[CustomPermissionAttribute(SecurityAction.LinkDemand)]  
public static string ReadData()  
{  
    // Access a custom resource.  
}  
```  
  
## Vea también  
 [Atributos](../../../docs/standard/attributes/index.md)   
 [Code Access Security](../../../docs/framework/misc/code-access-security.md)