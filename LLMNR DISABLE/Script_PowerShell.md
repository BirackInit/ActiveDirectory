#### Créer une nouvelle clé de registre :
   ```
   New-Item "HKLM:\SOFTWARE\Policies\Microsoft\Windows NT\DNSClient" -Force
  ```

#### Définir la valeur pour désactiver LLMNR :
```
New-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows NT\DNSClient" -Name EnableMulticast -Value 0 -PropertyType DWORD -Force
```


#### Redémarrer l'ordinateur pour appliquer les modifications si nécessaire :
```
Restart-Computer
```

#### Après le redémarrage, vous pouvez vérifier si LLMNR est désactivé en utilisant la commande suivante :

```
Get-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows NT\DNSClient" -Name EnableMulticast
```
