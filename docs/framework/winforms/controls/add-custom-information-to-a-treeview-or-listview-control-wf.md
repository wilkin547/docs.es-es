---
title: "C&#243;mo: Agregar informaci&#243;n personalizada a los controles TreeView o ListView (formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ListItem"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ejemplos [Windows Forms], ListView (control)"
  - "ejemplos [Windows Forms], TreeView (control)"
  - "ListView (control) [Windows Forms], agregar información personalizada"
  - "Tag (propiedad)"
  - "TreeView (control) [Windows Forms], agregar información personalizada"
ms.assetid: 68be11de-1d5b-430e-901f-cfbe48d14b19
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Agregar informaci&#243;n personalizada a los controles TreeView o ListView (formularios Windows Forms)
Puede crear un nodo derivado en un control <xref:System.Windows.Forms.TreeView> de formularios Windows Forms o un elemento derivado en un control <xref:System.Windows.Forms.ListView>.  La derivación permite agregar cualquier campo que se necesite, así como métodos personalizados y constructores para controlarlos.  Uno de los usos de esta característica consiste en adjuntar un objeto Customer a cada nodo de árbol o elemento de la lista.  Los ejemplos mostrados aquí son para un control <xref:System.Windows.Forms.TreeView>, pero podría utilizarse el mismo enfoque para un control <xref:System.Windows.Forms.ListView>.  
  
### Para derivar un nodo de árbol  
  
-   Cree una nueva clase de nodo, derivada de la clase <xref:System.Windows.Forms.TreeNode>, que tenga un campo personalizado para registrar una ruta de acceso a archivos.  
  
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
  
### Para utilizar un nodo de árbol derivado  
  
1.  Puede utilizar el nuevo nodo de árbol derivado como parámetro para llamadas de función.  
  
     En el ejemplo siguiente, la ruta de acceso establecida para la ubicación del archivo de texto es la carpeta Mis documentos.  Se utiliza esta ubicación porque se puede suponer que la mayoría de los equipos que ejecuten el sistema operativo Windows tendrán este directorio.  Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de un modo seguro.  
  
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
    treeView1.Nodes.Add(new myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
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
  
2.  Si se pasa el nodo de árbol y se escribe como una clase <xref:System.Windows.Forms.TreeNode>, deberá convertirlo en la clase derivada.  La conversión de tipos es una conversión explícita de un tipo de objeto a otro.  Para obtener más información sobre la conversión, vea [Conversiones implícitas y explícitas](../Topic/Implicit%20and%20Explicit%20Conversions%20\(Visual%20Basic\).md) \([!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\), [\(\) \(operador\)](../Topic/\(\)%20Operator%20\(C%23%20Reference\).md) \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\) o [Operador de conversión: \(\)](../../../../amples/snippets/visualbasic/VS_Snippets_Wpf/DocumentStructure/visualbasic/spec_withstructure-xps/_rels/.rels) \([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\).  
  
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
  
## Vea también  
 [TreeView \(Control\)](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [ListView \(Control\)](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)