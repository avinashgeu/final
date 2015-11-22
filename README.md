
Imports System.Data.SqlClient
Public Class Form1

    Private Sub Search_Click(sender As Object, e As EventArgs)

    End Sub

    Private Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
        If TextBox1.Text = "" Or Me.RadioButton1.Checked = False And Me.RadioButton2.Checked = False And Me.RadioButton3.Checked = False Or Me.TextBox2.Text = "" Then
            MsgBox("Warning ! Please fill all ...", MsgBoxStyle.Information)
            Exit Sub
        End If




        If RadioButton1.Checked = True Then

            Dim connectionString As String = "Data Source=AVINASH-PC;Initial Catalog=baby;Integrated Security=SSPI"

            Dim sql As String = "select * from ml where Given_Name Like '%" & Me.TextBox1.Text & "%' AND Year >= " & Me.TextBox2.Text & " AND Year <= 2013"
            Dim connection As New SqlConnection(connectionString)
            Dim dataadapter As New SqlDataAdapter(sql, connection)
            Dim ds As New DataSet()
            connection.Open()
            dataadapter.Fill(ds, "t1")
            connection.Close()
            DataGridView1.DataSource = ds
            DataGridView1.DataMember = "t1"
            connection.Close()

            ' MyCommand = New System.Data.OleDb.OleDbDataAdapter("select * from [ml$] where Given_Name Like '%" & Me.TextBox1.Text & "%' AND Year >= " & Me.TextBox2.Text & " AND Year <= 2013 ", MyConnection)





        ElseIf RadioButton2.Checked = True Then
            '        MyCommand = New System.Data.OleDb.OleDbDataAdapter("select * from [fem$] where Given_Name Like '%" & Me.TextBox1.Text & "%' AND Year >= " & Me.TextBox2.Text & " AND Year <= 2013 ", MyConnection)
            Dim connectionString As String = "Data Source=AVINASH-PC;Initial Catalog=baby;Integrated Security=SSPI"

            Dim sql As String = "select * from fem where Given_Name Like '%" & Me.TextBox1.Text & "%' AND Year >= " & Me.TextBox2.Text & " AND Year <= 2013"
            Dim connection As New SqlConnection(connectionString)
            Dim dataadapter As New SqlDataAdapter(sql, connection)
            Dim ds As New DataSet()
            connection.Open()
            dataadapter.Fill(ds, "t1")
            connection.Close()
            DataGridView1.DataSource = ds
            DataGridView1.DataMember = "t1"
            connection.Close()



        ElseIf RadioButton3.Checked = True Then

            '  MyCommand = New System.Data.OleDb.OleDbDataAdapter("select * from [both$] where Given_Name Like '%" & Me.TextBox1.Text & "%' AND Year >= " & Me.TextBox2.Text & " AND Year <= 2013 ", MyConnection)

            Dim connectionString As String = "Data Source=AVINASH-PC;Initial Catalog=baby;Integrated Security=SSPI"

            Dim sql As String = "select * from both where Given_Name Like '%" & Me.TextBox1.Text & "%' AND Year >= " & Me.TextBox2.Text & " AND Year <= 2013"
            Dim connection As New SqlConnection(connectionString)
            Dim dataadapter As New SqlDataAdapter(sql, connection)
            Dim ds As New DataSet()
            connection.Open()
            dataadapter.Fill(ds, "t1")
            connection.Close()
            DataGridView1.DataSource = ds
            DataGridView1.DataMember = "t1"
            connection.Close()

        End If


    End Sub

    Private Sub Button2_Click(sender As Object, e As EventArgs) Handles Button2.Click

        If Me.TextBox3.Text = "" Or Me.ComboBox1.Text = "" Then
            MsgBox("Warning ! Please fill all entries...", MsgBoxStyle.Information)
            Exit Sub
        End If



        ' MyCommand = New System.Data.OleDb.OleDbDataAdapter("select * from [both$] where year = 1944", MyConnection)


        ' MyCommand = New System.Data.OleDb.OleDbDataAdapter("select * from [fem$] where (Pos BETWEEN 1 AND 5) AND (Year BETWEEN 1944 AND 2013) ", MyConnection)
        'MyCommand = New System.Data.OleDb.OleDbDataAdapter("select * from [fem1$]", MyConnection)



        Dim connectionString As String = "Data Source=AVINASH-PC;Initial Catalog=baby;Integrated Security=SSPI"

        Dim sql As String = "select * from both where (Pos BETWEEN 1 AND " & Me.ComboBox1.Text & ") AND (Year BETWEEN " & Me.TextBox3.Text & " AND 2013)"
        Dim connection As New SqlConnection(connectionString)
        Dim dataadapter As New SqlDataAdapter(sql, connection)
        Dim ds As New DataSet()
        connection.Open()
        dataadapter.Fill(ds, "t1")
        connection.Close()
        DataGridView1.DataSource = ds
        DataGridView1.DataMember = "t1"
        connection.Close()



    End Sub

    Private Sub Button3_Click(sender As Object, e As EventArgs) Handles Button3.Click
        chart.Show()
    End Sub

    Private Sub DataGridView1_CellContentClick(sender As Object, e As DataGridViewCellEventArgs) Handles DataGridView1.CellContentClick

    End Sub

    Private Sub Label1_Click(sender As Object, e As EventArgs) Handles Label1.Click

    End Sub

    Private Sub RadioButton1_CheckedChanged(sender As Object, e As EventArgs) Handles RadioButton1.CheckedChanged

    End Sub

    Private Sub RadioButton3_CheckedChanged(sender As Object, e As EventArgs) Handles RadioButton3.CheckedChanged

    End Sub

    Private Sub Label2_Click(sender As Object, e As EventArgs) Handles Label2.Click

    End Sub
End Class
