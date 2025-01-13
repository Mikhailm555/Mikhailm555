<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Document</title>
</head>
<body>
	<?php
	$host = 'localhost';
	$db = 'up_pervushkinnss';
	$user = 'root';
	$pass = '';

	$mysqli = new mysqli($host, $user, $pass, $db);

	if ($mysqli->connect_error) {
		die("Ошибка подключения: " . $mysqli->connect_error);	



	$sql = "SELECT * FROM employees";
	$result = $mysqli->query($sql);

	if ($result->num_rows > 0) {
		echo "<table border='1'>
		<tr>
		<th>Код сотрудника<th>
		<th>ФИО<th>
		<th>Оклад<th>
		<th>Паспортные данные<th>
		<th>Дата рождения<th>
		<th>Адрес<th>
		<th>Пол<th>
		<th>Телефон<th>
		<th>ИНН<th>
		<th>Должность<th>
		</tr>";

		while($row = $result->fetch_assoc()) {
			echo "<tr>
			<td>" . $row["Код сотрудника"] . "</td>
			<td>" . $row["ФИО"] . "</td>
			<td>" . $row["Оклад"] . "</td>
			<td>" . $row["Паспортные данные"] . "</td>
			<td>" . $row["Дата рождения"] . "</td>
			<td>" . $row["Адрес"] . "</td>
			<td>" . $row["Пол"] . "</td>
			<td>" . $row["Телефон"] . "</td>
			<td>" . $row["ИНН"] . "</td>
			<td>" . $row["Должность"] . "</td>
			</tr>";
		}
	}
		echo "</table";
	}
	$mysqli->close();
?>
</body>
</html>
