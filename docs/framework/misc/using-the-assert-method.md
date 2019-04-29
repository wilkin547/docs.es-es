---
title: Utilizar el método Assert
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- granting permissions, overriding security checks
- code access security, overriding security checks
- overriding security checks
- security [.NET Framework], overriding security checks
- security [.NET Framework], assertions
- asserted permissions
- Assert method
- caller security checks
- permissions [.NET Framework], overriding security checks
- permissions [.NET Framework], assertions
ms.assetid: 1e40f4d3-fb7d-4f19-b334-b6076d469ea9
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 08b46d96f9fb950602766639559a375a25747010
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61869022"
---
# <a name="using-the-assert-method"></a>Utilizar el método Assert
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <xref:System.Security.CodeAccessPermission.Assert%2A> es un método al que se puede llamar en las clases de permiso de acceso a código y en la clase <xref:System.Security.PermissionSet>. Puede usar **Assert** habilitar el código (y los llamadores indirectos) realizar las acciones que el código tiene permiso para hacerlo, pero sus llamadores que no tenga permiso para realizar. Una aserción o validación de seguridad cambia el proceso normal que realiza el runtime durante una comprobación de seguridad. Al validar un permiso, se indica al sistema de seguridad que no compruebe los llamadores de su código para el permiso validado.  
  
> [!CAUTION]
>  Use las aserciones con cuidado, ya que crean vulnerabilidades de seguridad y minan el mecanismo de runtime para imponer las restricciones de seguridad.  
  
 Las aserciones son útiles en situaciones en las que una biblioteca llama a código no administrado o realiza una llamada que requiere un permiso que no está claramente relacionado con el uso previsto de la biblioteca. Por ejemplo, todo el código administrado que las llamadas a código no administrado deben tener **SecurityPermission** con el **UnmanagedCode** marca especificada. No concederá este permiso de forma predeterminada al código que no se origine en el equipo local, como es el caso del código que se descarga desde la intranet local. Por lo tanto, para que el código descargado de la intranet local pueda llamar a una biblioteca que usa código no administrado, la biblioteca debe validar el permiso. Además, algunas bibliotecas podrían realizar llamadas invisibles para los llamadores y que requieren permisos especiales.  
  
 También puede utilizar aserciones en situaciones en las que el código accede a un recurso de tal forma que queda totalmente oculto para los llamadores. Por ejemplo, suponga que su biblioteca adquiere información de una base de datos, pero al hacerlo también lee información del registro del equipo. Dado que los desarrolladores que usan la biblioteca no tienen acceso a su origen, no disponen de ninguna manera de saber que el código requiere **RegistryPermission** para poder usar el código. En este caso, si decide que no es razonable o necesario exigir que los llamadores del código tengan permiso para acceder al registro, puede validar el permiso de lectura del registro. En esta situación, es adecuado para que la biblioteca que valide el permiso para que los llamadores sin **RegistryPermission** puede usar la biblioteca.  
  
 La aserción afecta al recorrido de pila solo si el permiso validado y un permiso exigido por un llamador indirecto son del mismo tipo y si el permiso exigido es un subconjunto del permiso validado. Por ejemplo, si valida **FileIOPermission** leer todos los archivos en la unidad C y una demanda de nivel inferior se realiza **FileIOPermission** para leer los archivos de C:\Temp, la aserción podría afectar el recorrido de pila; Sin embargo, si la petición era para **FileIOPermission** para escribir en la unidad C, la aserción no tendría efecto.  
  
 Para realizar aserciones, el código debe disponer del permiso que usted está validando y el <xref:System.Security.Permissions.SecurityPermission> que representa el derecho a realizar aserciones. Aunque podría validar un permiso que no se haya concedido al código, la aserción no tendría sentido, ya que la comprobación de seguridad no se podría realizar correctamente antes de que la aserción pudiese lograr que se procesase debidamente.  
  
 La siguiente ilustración muestra lo que sucede cuando se usa **Assert**. Supongamos que son ciertas las siguientes declaraciones sobre los ensamblados A, B, C, E y F y los permisos P1 y P1A:  
  
- P1A representa el derecho a leer archivos .txt de la unidad C.  
  
- P1 representa el derecho a leer todos los archivos de la unidad C.  
  
- Tanto P1A como P1 son **FileIOPermission** tipos y P1A es un subconjunto de P1.  
  
- Se ha concedido el permiso P1A a los ensamblados E y F.  
  
- Se ha concedido el permiso P1 al ensamblado C.  
  
- No se ha concedido ni el permiso P1 ni el P1A a los ensamblados A y B.  
  
- El método A está incluido en el ensamblado A, el método B incluido en el ensamblado B, y así sucesivamente.  
  
 ![Diagrama que muestra los ensamblados del método Assert.](./media/using-the-assert-method/assert-method-assemblies.gif)    
  
 En este escenario de método A llama a B, B llama a C, C llama a E y E llama F. método C valida el permiso para leer archivos en la unidad C (permiso P1) y el método E solicita permiso para leer archivos .txt de la unidad C (permiso P1A). Cuando se detecta la petición en F en tiempo de ejecución, se realiza un recorrido de pila para comprobar los permisos de todos los llamadores de F, empezando por E. E concedió permiso P1A, por lo que el recorrido de pila pasa a examinar los permisos de C, donde se descubre la aserción de c. Dado que el permiso solicitado (P1A) es un subconjunto del permiso validado (P1), el recorrido de pila se detiene y se supera automáticamente la comprobación de seguridad. No importa que los ensamblados A y B no dispongan del permiso P1A. Al validar el permiso P1, el método C garantiza que sus llamadores puedan acceder al recurso protegido por P1, aunque los llamadores no tengan permiso para acceder a ese recurso.  
  
 Si diseña una biblioteca de clases y una clase obtiene acceso a un recurso protegido, debería, en la mayoría de los casos, realizar una petición de seguridad que requiera que los llamadores de la clase dispongan del permiso adecuado. Si la clase, a continuación, realiza una operación para que usted sabe que la mayoría de los llamadores no tendrán permiso, y si está dispuesto a asumir la responsabilidad de dejar que estos llamadores llamen al código, puede validar el permiso mediante una llamada a la **Assert** método en un objeto de permiso que representa la operación que está realizando el código. Uso de **Assert** de esta manera permite que los llamadores que normalmente no podrían llamar a su código. Por tanto, si valida un permiso, debe asegurarse de realizar previamente las comprobaciones de seguridad adecuadas para impedir que el componente se utilice incorrectamente.  
  
 Por ejemplo, suponga que su clase de biblioteca de mucha confianza tiene un método que elimina los archivos. Accede al archivo llamando a una función Win32 no administrada. Un llamador invoca el código **eliminar** método, pasando el nombre del archivo que se va a eliminar, C:\Test.txt. Dentro de la **eliminar** método, el código crea un <xref:System.Security.Permissions.FileIOPermission> objeto que representa el acceso de escritura a C:\Test.txt. (Se requiere acceso de escritura para eliminar un archivo). El código, a continuación, invoca una comprobación de seguridad imperativa llamando el **FileIOPermission** del objeto **demanda** método. Si uno de los llamadores de la pila de llamadas no tiene este permiso, se genera una <xref:System.Security.SecurityException>. Si no se genera ninguna excepción, sabe que todos los llamadores tienen derecho a acceder a C:\Test.txt. Dado que cree que la mayoría de los llamadores no tendrán permiso para tener acceso a código no administrado, el código, a continuación, crea un <xref:System.Security.Permissions.SecurityPermission> objeto que representa el derecho para llamar a código no administrado y llama al objeto **Assert** método. Por último, llama a la función de Win32 no administrada para eliminar C:\Text.txt y devuelve el control al llamador.  
  
> [!CAUTION]
>  Asegúrese de que su código no utilice aserciones en situaciones en las que su código pueda ser utilizado por otro código para acceder a un recurso que está protegido por el permiso que está validando. Por ejemplo, en el código que escribe en un archivo cuyo nombre se especifica por el llamador como un parámetro, no debería validar la **FileIOPermission** para escribir en archivos porque su código quedaría expuesto al mal uso por un tercero.  
  
 Cuando se usa la sintaxis de seguridad imperativa, llamar a la **Assert** método en varios permisos en el mismo método hace que se produzca una excepción de seguridad. En su lugar, debe crear un **PermissionSet** de objetos, pasarle los permisos individuales que desea invocar y, a continuación, llamar a la **Assert** método en el **PermissionSet** objeto. Puede llamar a la **Assert** método más de una vez cuando se usa la sintaxis de seguridad declarativa.  
  
 El ejemplo siguiente muestra una sintaxis declarativa para omitir comprobaciones de seguridad mediante la **Assert** método. Tenga en cuenta que el **FileIOPermissionAttribute** sintaxis toma dos valores: una <xref:System.Security.Permissions.SecurityAction> enumeración y la ubicación del archivo o directorio al que se va a conceder permiso. La llamada a **Assert** hace que las peticiones para tener acceso a `C:\Log.txt` se realice correctamente, aunque no se comprueban los llamadores para que obtener permiso para tener acceso al archivo.  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.IO  
Imports System.Security.Permissions  
  
Namespace LogUtil  
   Public Class Log  
      Public Sub New()  
  
      End Sub  
  
     <FileIOPermission(SecurityAction.Assert, All := "C:\Log.txt")> Public Sub   
      MakeLog()  
         Dim TextStream As New StreamWriter("C:\Log.txt")  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now) '  
         TextStream.Close()  
      End Sub  
   End Class  
End Namespace  
```  
  
```csharp  
namespace LogUtil  
{  
   using System;  
   using System.IO;  
   using System.Security.Permissions;  
  
   public class Log  
   {  
      public Log()  
      {      
      }     
      [FileIOPermission(SecurityAction.Assert, All = @"C:\Log.txt")]  
      public void MakeLog()  
      {     
         StreamWriter TextStream = new StreamWriter(@"C:\Log.txt");  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now);  
         TextStream.Close();  
      }  
   }  
}   
```  
  
 Los fragmentos de código siguiente muestran la sintaxis declarativa para omitir comprobaciones de seguridad mediante la **Assert** método. En este ejemplo, una instancia de la **FileIOPermission** se declara el objeto. Se pasa a su constructor **FileIOPermissionAccess.AllAccess** definir el tipo de acceso permitido, seguido de una cadena que describe la ubicación del archivo. Una vez el **FileIOPermission** objeto está definido, solo necesita llamar a su **Assert** método para invalidar la comprobación de seguridad.  
  
```vb  
Option Explicit  
Option Strict  
Imports System  
Imports System.IO  
Imports System.Security.Permissions  
Namespace LogUtil  
   Public Class Log  
      Public Sub New()  
      End Sub 'New  
  
      Public Sub MakeLog()  
         Dim FilePermission As New FileIOPermission(FileIOPermissionAccess.AllAccess, "C:\Log.txt")  
         FilePermission.Assert()  
         Dim TextStream As New StreamWriter("C:\Log.txt")  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now)  
         TextStream.Close()  
      End Sub  
   End Class  
End Namespace  
```  
  
```csharp  
namespace LogUtil  
{  
   using System;  
   using System.IO;  
   using System.Security.Permissions;  
  
   public class Log  
   {  
      public Log()  
      {      
      }     
      public void MakeLog()  
      {  
         FileIOPermission FilePermission = new FileIOPermission(FileIOPermissionAccess.AllAccess,@"C:\Log.txt");   
         FilePermission.Assert();  
         StreamWriter TextStream = new StreamWriter(@"C:\Log.txt");  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now);  
         TextStream.Close();  
      }  
   }  
}  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Security.PermissionSet>
- <xref:System.Security.Permissions.SecurityPermission>
- <xref:System.Security.Permissions.FileIOPermission>
- <xref:System.Security.Permissions.SecurityAction>
- [Atributos](../../../docs/standard/attributes/index.md)
- [Seguridad de acceso del código](../../../docs/framework/misc/code-access-security.md)
