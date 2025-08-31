## Task 3.4

`kubectl apply -f backend-pod.yaml`

`kubectl get pods`

### Result:

<img width="890" height="62" alt="image" src="https://github.com/user-attachments/assets/d728077e-aefa-47ad-a1cd-ed5d95e7ae72" />


`kubectl delete pod backend`

<img width="1000" height="84" alt="image" src="https://github.com/user-attachments/assets/75cd3f8e-94af-42a0-8bbc-c0ef933a24a2" />


## Task 3.5
### Tworzenie przestrzeni nazw:

`kubectl create namespace nginx-ns`


<img width="1057" height="33" alt="image" src="https://github.com/user-attachments/assets/4a14d0bd-93f7-44f4-8e3f-c41e99d74bcc" />

### Wykonanie polecenia:

`kubectl -n nginx-ns create deployment --image=nginx nginx-app`
<img width="1094" height="47" alt="image" src="https://github.com/user-attachments/assets/282ecb47-1c25-4fb3-8c02-5b8bd8e92d81" />

### Wyświetlenie wszystkich deployments

`kubectl get deployments -n nginx-ns`

<img width="518" height="40" alt="image" src="https://github.com/user-attachments/assets/8da1d8b5-2503-44d3-83ab-d22a9e64d00c" />

### Szczegółowe informcje o deployment:

`kubectl describe deployment nginx-app -n nginx-ns`

<img width="1142" height="590" alt="image" src="https://github.com/user-attachments/assets/32c0057e-f0a3-46ba-bd6c-fd881ee4a7e3" />

### Wyświetlanie nazw podów w przestrzeni nginx-ns

`kubectl get pods -n nginx-ns -o custom-columns=NAME:.metadata.name`

<img width="263" height="42" alt="image" src="https://github.com/user-attachments/assets/8e86bead-faea-4a31-a14e-0566c4837526" />

### Wyświetlenie manifest YAML dla utworzonego deploymentu

`kubectl get deployment nginx-app -n nginx-ns -o yaml`

<img width="508" height="707" alt="image" src="https://github.com/user-attachments/assets/558adf85-cf45-4320-aaf3-5d0ba1caa22d" />

### Wypisanie zawartości pliku /etc/hosts z istniejącego poda

#### Pozyskanie nazwy poda: 
`kubectl get pods -n nginx-ns`

<img width="567" height="40" alt="image" src="https://github.com/user-attachments/assets/98b96d86-8ba6-4770-96c3-295e20e243e0" />

#### Wypisanie zawaerości dla poda o konretnej nazwie:
 
`kubectl exec -n nginx-ns nginx-app-5777b5f95-lfs82 -- cat /etc/hosts`

<img width="441" height="123" alt="image" src="https://github.com/user-attachments/assets/5bc7b573-6958-40d7-8255-4e0c0cb1880b" />

### Usunięcie istniejącego poda z przestrzeni nazw

`kubectl delete pod nginx-app-5777b5f95-lfs82 -n nginx-ns`

<img width="378" height="37" alt="image" src="https://github.com/user-attachments/assets/883601f0-e108-466e-a0bb-c89721d79287" />

### Usunięcie deploymentu:

`kubectl delete deployment nginx-app -n nginx-ns`

<img width="333" height="23" alt="image" src="https://github.com/user-attachments/assets/e1e8a7ea-a895-44e0-808a-c7b973909c19" />

### Usunięcie przestrezni nazw:

`kubectl delete ns nginx-ns`

<img width="275" height="37" alt="image" src="https://github.com/user-attachments/assets/a2ded320-2f31-4587-8fc3-c71bce8396e6" />






