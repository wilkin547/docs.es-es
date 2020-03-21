---
title: 'Cómo: Agregar información personalizada a un Control TreeView o ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- ListItem
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- examples [Windows Forms], ListView control
- ListView control [Windows Forms], adding custom information
- TreeView control [Windows Forms], adding custom information
ms.assetid: 68be11de-1d5b-430e-901f-cfbe48d14b19
ms.openlocfilehash: faed586a5814526b0169ea46c8bb452e3777d8ba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182432"
---
# <a name="how-to-add-custom-information-to-a-treeview-or-listview-control-windows-forms"></a>Cómo: Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)
Puede crear un nodo derivado en <xref:System.Windows.Forms.TreeView> un control de formularios <xref:System.Windows.Forms.ListView> Windows Forms o un elemento derivado en un control. La derivación permite agregar cualquier campo que se necesite, así como métodos personalizados y constructores para controlarlos. Uno de los usos de esta característica consiste en adjuntar un objeto Customer a cada nodo de árbol o elemento de lista. Los ejemplos aquí <xref:System.Windows.Forms.TreeView> son para un control, pero <xref:System.Windows.Forms.ListView> se puede usar el mismo enfoque para un control.  
  
### <a name="to-derive-a-tree-node"></a>Para derivar un nodo de árbol  
  
- Cree una nueva clase de nodo, derivada de la <xref:System.Windows.Forms.TreeNode> clase, que tiene un campo personalizado para registrar una ruta de acceso de archivo.  
  
    ```vb  
    Class myTreeNode  
       Inherits TreeNode  
  
       Public FilePath As String  
  
       Sub New(ByVal fp As String)  
          MyBase.New()  
          FilePath = fp  
          Me.Text = fp.Substring(fp.LastIndexOf("\"))  
       End Sub  
    End Class  
    ```  
  
    ```csharp  
    class myTreeNode : TreeNode  
    {  
       public string FilePath;  
  
       public myTreeNode(string fp)  
       {  
          FilePath = fp;  
          this.Text = fp.Substring(fp.LastIndexOf("\\"));  
       }  
    }  
    ```  
  
    ```cpp  
    ref class myTreeNode : public TreeNode  
    {  
    public:  
       System::String ^ FilePath;  
  
       myTreeNode(System::String ^ fp)  
       {  
          FilePath = fp;  
          this->Text = fp->Substring(fp->LastIndexOf("\\"));  
       }  
    };  
    ```  
  
### <a name="to-use-a-derived-tree-node"></a>Para utilizar un nodo de árbol derivado  
  
1. Puede utilizar el nuevo nodo de árbol derivado como parámetro para llamadas de función.  
  
     En el ejemplo siguiente, la ruta de acceso establecida para la ubicación del archivo de texto es la carpeta Mis documentos. Se utiliza esta ubicación porque se puede suponer que la mayoría de los equipos que ejecuten el sistema operativo Windows tendrán este directorio. Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura.  
  
    ```vb  
    ' You should replace the bold text file
    ' in the sample below with a text file of your own choosing.  
    TreeView1.Nodes.Add(New myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\ TextFile.txt ") )  
    ```  
  
    ```csharp  
    // You should replace the bold text file
    // in the sample below with a text file of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    treeView1.Nodes.Add(new myTreeNode(System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\TextFile.txt") );  
    ```  
  
    ```cpp  
    // You should replace the bold text file
    // in the sample below with a text file of your own choosing.  
    treeView1->Nodes->Add(new myTreeNode(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\TextFile.txt")));  
    ```  
  
2. Si se pasa el nodo de árbol y <xref:System.Windows.Forms.TreeNode> se escribe como una clase, tendrá que convertir a la clase derivada. La conversión de tipos es una conversión explícita de un tipo de objeto a otro. Para obtener más información sobre la conversión, vea [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) (Visual Basic), [Conversión y conversiones](../../../csharp/programming-guide/types/casting-and-type-conversions.md) de tipos (Visual C-) o Operador de [conversión: ()](/cpp/cpp/cast-operator-parens) (Visual C++).  
  
    ```vb  
    Public Sub TreeView1_AfterSelect(ByVal sender As Object, ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       Dim mynode As myTreeNode  
       mynode = CType(e.node, myTreeNode)  
       MessageBox.Show("Node selected is " & mynode.filepath)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,  
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       myTreeNode myNode = (myTreeNode)e.Node;  
       MessageBox.Show("Node selected is " + myNode.FilePath);  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          myTreeNode ^ myNode = safe_cast<myTreeNode^>(e->Node);  
          MessageBox::Show(String::Concat("Node selected is ",
             myNode->FilePath));  
       }  
    ```  
  
## <a name="see-also"></a>Consulte también

- [TreeView (control)](treeview-control-windows-forms.md)
- [Control ListView](listview-control-windows-forms.md)
