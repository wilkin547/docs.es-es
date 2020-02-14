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
ms.openlocfilehash: 2bc46714a508990c5ae31b50e7d19a287da2c5c0
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215819"
---
# <a name="using-the-assert-method"></a><span data-ttu-id="5aaa1-102">Utilizar el método Assert</span><span class="sxs-lookup"><span data-stu-id="5aaa1-102">Using the Assert Method</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="5aaa1-103"><xref:System.Security.CodeAccessPermission.Assert%2A> es un método al que se puede llamar en las clases de permiso de acceso a código y en la clase <xref:System.Security.PermissionSet>.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-103"><xref:System.Security.CodeAccessPermission.Assert%2A> is a method that can be called on code access permission classes and on the <xref:System.Security.PermissionSet> class.</span></span> <span data-ttu-id="5aaa1-104">Puede usar **Assert** para permitir que el código (y los llamadores de nivel inferior) realicen acciones para las que el código tiene permiso, pero es posible que sus llamadores no tengan permiso para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-104">You can use **Assert** to enable your code (and downstream callers) to perform actions that your code has permission to do but its callers might not have permission to do.</span></span> <span data-ttu-id="5aaa1-105">Una aserción o validación de seguridad cambia el proceso normal que realiza el runtime durante una comprobación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-105">A security assertion changes the normal process that the runtime performs during a security check.</span></span> <span data-ttu-id="5aaa1-106">Al validar un permiso, se indica al sistema de seguridad que no compruebe los llamadores de su código para el permiso validado.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-106">When you assert a permission, it tells the security system not to check the callers of your code for the asserted permission.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="5aaa1-107">Use las aserciones con cuidado, ya que crean vulnerabilidades de seguridad y minan el mecanismo de runtime para imponer las restricciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-107">Use assertions carefully because they can open security holes and undermine the runtime's mechanism for enforcing security restrictions.</span></span>  
  
 <span data-ttu-id="5aaa1-108">Las aserciones son útiles en situaciones en las que una biblioteca llama a código no administrado o realiza una llamada que requiere un permiso que no está claramente relacionado con el uso previsto de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-108">Assertions are useful in situations in which a library calls into unmanaged code or makes a call that requires a permission that is not obviously related to the library's intended use.</span></span> <span data-ttu-id="5aaa1-109">Por ejemplo, todo el código administrado que llama a código no administrado debe tener **SecurityPermission** con la marca **UnmanagedCode** especificada.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-109">For example, all managed code that calls into unmanaged code must have **SecurityPermission** with the **UnmanagedCode** flag specified.</span></span> <span data-ttu-id="5aaa1-110">No concederá este permiso de forma predeterminada al código que no se origine en el equipo local, como es el caso del código que se descarga desde la intranet local.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-110">Code that does not originate from the local computer, such as code that is downloaded from the local intranet, will not be granted this permission by default.</span></span> <span data-ttu-id="5aaa1-111">Por lo tanto, para que el código descargado de la intranet local pueda llamar a una biblioteca que usa código no administrado, la biblioteca debe validar el permiso.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-111">Therefore, in order for code that is downloaded from the local intranet to be able to call a library that uses unmanaged code, it must have the permission asserted by the library.</span></span> <span data-ttu-id="5aaa1-112">Además, algunas bibliotecas podrían realizar llamadas invisibles para los llamadores y que requieren permisos especiales.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-112">Additionally, some libraries might make calls that are unseen to callers and require special permissions.</span></span>  
  
 <span data-ttu-id="5aaa1-113">También puede utilizar aserciones en situaciones en las que el código accede a un recurso de tal forma que queda totalmente oculto para los llamadores.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-113">You can also use assertions in situations in which your code accesses a resource in a way that is completely hidden from callers.</span></span> <span data-ttu-id="5aaa1-114">Por ejemplo, suponga que su biblioteca adquiere información de una base de datos, pero al hacerlo también lee información del registro del equipo.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-114">For example, suppose your library acquires information from a database, but in the process also reads information from the computer registry.</span></span> <span data-ttu-id="5aaa1-115">Dado que los desarrolladores que usan su biblioteca no tienen acceso al origen, no tienen ninguna manera de saber que su código requiere **RegistryPermission** para usar el código.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-115">Because developers using your library do not have access to your source, they have no way of knowing that their code requires **RegistryPermission** in order to use your code.</span></span> <span data-ttu-id="5aaa1-116">En este caso, si decide que no es razonable o necesario exigir que los llamadores del código tengan permiso para acceder al registro, puede validar el permiso de lectura del registro.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-116">In this case, if you decide that it is not reasonable or necessary to require that callers of your code have permission to access the registry, you can assert permission for reading the registry.</span></span> <span data-ttu-id="5aaa1-117">En esta situación, es adecuado que la biblioteca imponga el permiso para que los llamadores sin **RegistryPermission** puedan utilizar la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-117">In this situation, it is appropriate for the library to assert the permission so that callers without **RegistryPermission** can use the library.</span></span>  
  
 <span data-ttu-id="5aaa1-118">La aserción afecta al recorrido de pila solo si el permiso validado y un permiso exigido por un llamador indirecto son del mismo tipo y si el permiso exigido es un subconjunto del permiso validado.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-118">The assertion affects the stack walk only if the asserted permission and a permission demanded by a downstream caller are of the same type and if the demanded permission is a subset of the asserted permission.</span></span> <span data-ttu-id="5aaa1-119">Por ejemplo, si se valida **FileIOPermission** para leer todos los archivos de la unidad C y se realiza una petición de nivel inferior para **FileIOPermission** para leer archivos en C:\temp, la aserción podría afectar al recorrido de la pila; sin embargo, si la demanda era de **FileIOPermission** para escribir en la unidad C, la aserción no tendría ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-119">For example, if you assert **FileIOPermission** to read all files on the C drive, and a downstream demand is made for **FileIOPermission** to read files in C:\Temp, the assertion could affect the stack walk; however, if the demand was for **FileIOPermission** to write to the C drive, the assertion would have no effect.</span></span>  
  
 <span data-ttu-id="5aaa1-120">Para realizar aserciones, el código debe disponer del permiso que usted está validando y el <xref:System.Security.Permissions.SecurityPermission> que representa el derecho a realizar aserciones.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-120">To perform assertions, your code must be granted both the permission you are asserting and the <xref:System.Security.Permissions.SecurityPermission> that represents the right to make assertions.</span></span> <span data-ttu-id="5aaa1-121">Aunque podría validar un permiso que no se haya concedido al código, la aserción no tendría sentido, ya que la comprobación de seguridad no se podría realizar correctamente antes de que la aserción pudiese lograr que se procesase debidamente.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-121">Although you could assert a permission that your code has not been granted, the assertion would be pointless because the security check would fail before the assertion could cause it to succeed.</span></span>  
  
 <span data-ttu-id="5aaa1-122">En la ilustración siguiente se muestra lo que sucede cuando se usa **Assert**.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-122">The following illustration shows what happens when you use **Assert**.</span></span> <span data-ttu-id="5aaa1-123">Supongamos que son ciertas las siguientes declaraciones sobre los ensamblados A, B, C, E y F y los permisos P1 y P1A:</span><span class="sxs-lookup"><span data-stu-id="5aaa1-123">Assume that the following statements are true about assemblies A, B, C, E, and F, and two permissions, P1 and P1A:</span></span>  
  
- <span data-ttu-id="5aaa1-124">P1A representa el derecho a leer archivos .txt de la unidad C.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-124">P1A represents the right to read .txt files on the C drive.</span></span>  
  
- <span data-ttu-id="5aaa1-125">P1 representa el derecho a leer todos los archivos de la unidad C.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-125">P1 represents the right to read all files on the C drive.</span></span>  
  
- <span data-ttu-id="5aaa1-126">P1A y P1 son tipos **FileIOPermission** y P1A es un subconjunto de P1.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-126">P1A and P1 are both **FileIOPermission** types, and P1A is a subset of P1.</span></span>  
  
- <span data-ttu-id="5aaa1-127">Se ha concedido el permiso P1A a los ensamblados E y F.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-127">Assemblies E and F have been granted P1A permission.</span></span>  
  
- <span data-ttu-id="5aaa1-128">Se ha concedido el permiso P1 al ensamblado C.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-128">Assembly C has been granted P1 permission.</span></span>  
  
- <span data-ttu-id="5aaa1-129">No se ha concedido ni el permiso P1 ni el P1A a los ensamblados A y B.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-129">Assemblies A and B have been granted neither P1 nor P1A permissions.</span></span>  
  
- <span data-ttu-id="5aaa1-130">El método A está incluido en el ensamblado A, el método B incluido en el ensamblado B, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-130">Method A is contained in assembly A, method B is contained in assembly B, and so on.</span></span>  
  
 ![Diagrama que muestra los ensamblados del método Assert.](./media/using-the-assert-method/assert-method-assemblies.gif)    
  
 <span data-ttu-id="5aaa1-132">En este escenario, el método A llama a B, B llama a C, C llama a E y E llama a F. el método C valida el permiso para leer archivos en la unidad C (permiso P1) y el método E solicita permiso para leer archivos. txt en la unidad C (permiso P1A).</span><span class="sxs-lookup"><span data-stu-id="5aaa1-132">In this scenario, method A calls B, B calls C, C calls E, and E calls F. Method C asserts permission to read files on the C drive (permission P1), and method E demands permission to read .txt files on the C drive (permission P1A).</span></span> <span data-ttu-id="5aaa1-133">Cuando se encuentra la petición en F en tiempo de ejecución, se realiza un recorrido de pila para comprobar los permisos de todos los llamadores de F, a partir de E. E, se le ha concedido el permiso P1A, por lo que el recorrido de la pila continúa para examinar los permisos de C, donde se detecta la aserción de C.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-133">When the demand in F is encountered at run time, a stack walk is performed to check the permissions of all callers of F, starting with E. E has been granted P1A permission, so the stack walk proceeds to examine the permissions of C, where C's assertion is discovered.</span></span> <span data-ttu-id="5aaa1-134">Dado que el permiso solicitado (P1A) es un subconjunto del permiso validado (P1), el recorrido de pila se detiene y se supera automáticamente la comprobación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-134">Because the demanded permission (P1A) is a subset of the asserted permission (P1), the stack walk stops and the security check automatically succeeds.</span></span> <span data-ttu-id="5aaa1-135">No importa que los ensamblados A y B no dispongan del permiso P1A.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-135">It does not matter that assemblies A and B have not been granted permission P1A.</span></span> <span data-ttu-id="5aaa1-136">Al validar el permiso P1, el método C garantiza que sus llamadores puedan acceder al recurso protegido por P1, aunque los llamadores no tengan permiso para acceder a ese recurso.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-136">By asserting P1, method C ensures that its callers can access the resource protected by P1, even if the callers have not been granted permission to access that resource.</span></span>  
  
 <span data-ttu-id="5aaa1-137">Si diseña una biblioteca de clases y una clase obtiene acceso a un recurso protegido, debería, en la mayoría de los casos, realizar una petición de seguridad que requiera que los llamadores de la clase dispongan del permiso adecuado.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-137">If you design a class library and a class accesses a protected resource, you should, in most cases, make a security demand requiring that the callers of the class have the appropriate permission.</span></span> <span data-ttu-id="5aaa1-138">Si la clase realiza una operación para la que sabe que la mayoría de los llamadores no tiene permiso, y si está dispuesto a asumir la responsabilidad de permitir que estos llamadores llamen al código, puede validar el permiso llamando al método **Assert** en un objeto de permiso que representa la operación que el código está realizando.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-138">If the class then performs an operation for which you know most of its callers will not have permission, and if you are willing to take the responsibility for letting these callers call your code, you can assert the permission by calling the **Assert** method on a permission object that represents the operation the code is performing.</span></span> <span data-ttu-id="5aaa1-139">El uso de **Assert** de esta manera permite a los llamadores que normalmente no podrían llamar a su código.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-139">Using **Assert** in this way lets callers that normally could not do so call your code.</span></span> <span data-ttu-id="5aaa1-140">Por tanto, si valida un permiso, debe asegurarse de realizar previamente las comprobaciones de seguridad adecuadas para impedir que el componente se utilice incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-140">Therefore, if you assert a permission, you should be sure to perform appropriate security checks beforehand to prevent your component from being misused.</span></span>  
  
 <span data-ttu-id="5aaa1-141">Por ejemplo, suponga que su clase de biblioteca de mucha confianza tiene un método que elimina los archivos.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-141">For example, suppose your highly trusted library class has a method that deletes files.</span></span> <span data-ttu-id="5aaa1-142">Accede al archivo llamando a una función Win32 no administrada.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-142">It accesses the file by calling an unmanaged Win32 function.</span></span> <span data-ttu-id="5aaa1-143">Un llamador invoca el método **Delete** del código, pasando el nombre del archivo que se va a eliminar, C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-143">A caller invokes your code's **Delete** method, passing in the name of the file to be deleted, C:\Test.txt.</span></span> <span data-ttu-id="5aaa1-144">Dentro del método **Delete** , el código crea un objeto <xref:System.Security.Permissions.FileIOPermission> que representa el acceso de escritura a C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-144">Within the **Delete** method, your code creates a <xref:System.Security.Permissions.FileIOPermission> object representing write access to C:\Test.txt.</span></span> <span data-ttu-id="5aaa1-145">(Se requiere acceso de escritura para eliminar un archivo). A continuación, el código invoca una comprobación de seguridad imperativa llamando al método **Demand** del objeto **FileIOPermission** .</span><span class="sxs-lookup"><span data-stu-id="5aaa1-145">(Write access is required to delete a file.) Your code then invokes an imperative security check by calling the **FileIOPermission** object's **Demand** method.</span></span> <span data-ttu-id="5aaa1-146">Si uno de los llamadores de la pila de llamadas no tiene este permiso, se genera una <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-146">If one of the callers in the call stack does not have this permission, a <xref:System.Security.SecurityException> is thrown.</span></span> <span data-ttu-id="5aaa1-147">Si no se genera ninguna excepción, sabe que todos los llamadores tienen derecho a acceder a C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-147">If no exception is thrown, you know that all callers have the right to access C:\Test.txt.</span></span> <span data-ttu-id="5aaa1-148">Como cree que la mayoría de los llamadores no tendrán permiso de acceso a código no administrado, el código crea un objeto <xref:System.Security.Permissions.SecurityPermission> que representa el derecho a llamar a código no administrado y llama al método **Assert** del objeto.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-148">Because you believe that most of your callers will not have permission to access unmanaged code, your code then creates a <xref:System.Security.Permissions.SecurityPermission> object that represents the right to call unmanaged code and calls the object's **Assert** method.</span></span> <span data-ttu-id="5aaa1-149">Por último, llama a la función de Win32 no administrada para eliminar C:\Text.txt y devuelve el control al llamador.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-149">Finally, it calls the unmanaged Win32 function to delete C:\Text.txt and returns control to the caller.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="5aaa1-150">Asegúrese de que su código no utilice aserciones en situaciones en las que su código pueda ser utilizado por otro código para acceder a un recurso que está protegido por el permiso que está validando.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-150">You must be sure that your code does not use assertions in situations where your code can be used by other code to access a resource that is protected by the permission you are asserting.</span></span> <span data-ttu-id="5aaa1-151">Por ejemplo, en el código que escribe en un archivo cuyo nombre se especifica mediante el autor de la llamada como un parámetro, no imponer el **FileIOPermission** para escribir en los archivos porque el código sería abierto para que un tercero no pueda utilizarlo.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-151">For example, in code that writes to a file whose name is specified by the caller as a parameter, you would not assert the **FileIOPermission** for writing to files because your code would be open to misuse by a third party.</span></span>  
  
 <span data-ttu-id="5aaa1-152">Cuando se usa la sintaxis de seguridad imperativa, al llamar al método **Assert** en varios permisos en el mismo método, se produce una excepción de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-152">When you use the imperative security syntax, calling the **Assert** method on multiple permissions in the same method causes a security exception to be thrown.</span></span> <span data-ttu-id="5aaa1-153">En su lugar, debe crear un objeto **PermissionSet** , pasarle los permisos individuales que desea invocar y, a continuación, llamar al método **Assert** en el objeto **PermissionSet** .</span><span class="sxs-lookup"><span data-stu-id="5aaa1-153">Instead, you should create a **PermissionSet** object, pass it the individual permissions you want to invoke, and then call the **Assert** method on the **PermissionSet** object.</span></span> <span data-ttu-id="5aaa1-154">Puede llamar al método **Assert** más de una vez al utilizar la sintaxis de seguridad declarativa.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-154">You can call the **Assert** method more than once when you use the declarative security syntax.</span></span>  
  
 <span data-ttu-id="5aaa1-155">En el ejemplo siguiente se muestra la sintaxis declarativa para invalidar las comprobaciones de seguridad mediante el método **Assert** .</span><span class="sxs-lookup"><span data-stu-id="5aaa1-155">The following example shows declarative syntax for overriding security checks using the **Assert** method.</span></span> <span data-ttu-id="5aaa1-156">Observe que la sintaxis de **FileIOPermissionAttribute** toma dos valores: una enumeración <xref:System.Security.Permissions.SecurityAction> y la ubicación del archivo o directorio al que se va a conceder el permiso.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-156">Notice that the **FileIOPermissionAttribute** syntax takes two values: a <xref:System.Security.Permissions.SecurityAction> enumeration and the location of the file or directory to which permission is to be granted.</span></span> <span data-ttu-id="5aaa1-157">La llamada a **Assert** hace que las peticiones de acceso a `C:\Log.txt` se realicen correctamente, aunque no se comprueba que los llamadores tengan permiso para obtener acceso al archivo.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-157">The call to **Assert** causes demands for access to `C:\Log.txt` to succeed, even though callers are not checked for permission to access the file.</span></span>  
  
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
  
 <span data-ttu-id="5aaa1-158">Los fragmentos de código siguientes muestran la sintaxis imperativa para invalidar las comprobaciones de seguridad mediante el método **Assert** .</span><span class="sxs-lookup"><span data-stu-id="5aaa1-158">The following code fragments show imperative syntax for overriding security checks using the **Assert** method.</span></span> <span data-ttu-id="5aaa1-159">En este ejemplo, se declara una instancia del objeto **FileIOPermission** .</span><span class="sxs-lookup"><span data-stu-id="5aaa1-159">In this example, an instance of the **FileIOPermission** object is declared.</span></span> <span data-ttu-id="5aaa1-160">Se pasa el constructor **FileIOPermissionAccess. AllAccess** para definir el tipo de acceso permitido, seguido de una cadena que describe la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-160">Its constructor is passed **FileIOPermissionAccess.AllAccess** to define the type of access allowed, followed by a string describing the file's location.</span></span> <span data-ttu-id="5aaa1-161">Una vez definido el objeto **FileIOPermission** , solo tiene que llamar a su método **Assert** para invalidar la comprobación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5aaa1-161">Once the **FileIOPermission** object is defined, you only need to call its **Assert** method to override the security check.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5aaa1-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5aaa1-162">See also</span></span>

- <xref:System.Security.PermissionSet>
- <xref:System.Security.Permissions.SecurityPermission>
- <xref:System.Security.Permissions.FileIOPermission>
- <xref:System.Security.Permissions.SecurityAction>
- [<span data-ttu-id="5aaa1-163">Atributos</span><span class="sxs-lookup"><span data-stu-id="5aaa1-163">Attributes</span></span>](../../standard/attributes/index.md)
- [<span data-ttu-id="5aaa1-164">Seguridad de acceso del código</span><span class="sxs-lookup"><span data-stu-id="5aaa1-164">Code Access Security</span></span>](code-access-security.md)
