Imports System.IO

Public Class Form1

    Private Sub btnSave_Click(sender As Object, e As EventArgs) Handles btnSave.Click
        Dim strFilePath = "C:\temp\code.xvb"

        SaveText(strFilePath)

        End

    End Sub

    Sub SaveText(path)

        Dim SWriter As New StreamWriter(path, False) 'false = don't append to an existing file

        SWriter.Write(TextBox1.Text)

        SWriter.Close()

    End Sub

    Function LoadText(path As String)

        If Not File.Exists(path) Then

            MsgBox("The xvb file was not found in " & path)

        End If

        Dim SReader As New StreamReader(path), strxvb

        strxvb = SReader.ReadToEnd()

        SReader.Close()

        Return xvb

    End Function

    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load

        Dim FilePath = "C:\temp\xvb.txt"

        TextBox1.Text = LoadText(FilePath)

    End Sub
End Class
