# Gestion des Erreurs en Go

Michel Casabianca

casa@sweetohm.net

---
## Slides Template Project

Considérons le source Go suivant :

```go
func printSum(a, b string) error {
	x, err := strconv.Atoi(a)
	if err != nil {
		return err
	}
	y, err := strconv.Atoi(b)
	if err != nil {
		return err
	}
	fmt.Println("result:", x + y)
	return nil
}
```

Sa gestion des erreurs est typique du Go : après chaque appel de fonction susceptible de renvoyer une erreur, on vérifie si elle s'est produite et on la renvoie à l'appelant, souvent accompagnée de valeurs nulles.

---
## Le problème

Le problème ici est que le code de gestion des erreurs est très verbeux et répétitif. C'est une corvée à laquelle aucun développeur Go ne peut se soustraire.

![](img/golang-clavier.png)

