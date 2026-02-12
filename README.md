# Enterprise Network Design


Ce projet montre la création d'un **réseau d'entreprise** avec **segmentation VLAN**, **routage inter-VLAN**, **configuration DHCP**, **NAT Overload (PAT)** et **contrôle des accès via ACLs** pour sécuriser les communications entre les départements. Le réseau est simulé à l'aide de Cisco Packet Tracer.

---

## Topologie
<img width="1513" height="1030" alt="image" src="https://github.com/user-attachments/assets/3f4199ea-82e2-4970-9153-221798c83a99" />

- **VLANs**:
  - VLAN 10: Marketing
  - VLAN 20: Sales
  - VLAN 30: IT
  - VLAN 40: Admin
  - VLAN 50: Servers
  - VLAN 99: MGMT (pour la gestion des switchs et du routeur)

- **Routage inter-VLAN** :
  - "Router on a Stick" (une interface physique de routeur pour plusieurs VLANs)

---

## Détails de la configuration

1. **Configuration des VLANs** :
   - `vlan 10` - Marketing
   - `vlan 20` - Sales
   - `vlan 30` - IT
   - `vlan 40` - Admin
   - `vlan 50` - Servers
   - `vlan 99` - MGMT (gestion des switchs et routeurs)

2. **Router on a Stick** :
   - Sous-interfaces pour chaque VLAN.
   - Adresses IP assignées à chaque sous-interface (passerelles VLAN).

3. **Configuration du DHCP** :
   - Pools DHCP créés pour chaque VLAN.
   - Adresses exclues pour éviter les conflits avec le routeur et les serveurs.

4. **Listes de Contrôle d'Accès (ACL)** :
   - Application des ACLs sur le routeur pour empêcher certains VLANs d'accéder aux serveurs.

5. **NAT Overload (PAT)** :
   - Simulation de l'accès à Internet.
   - Les adresses IP privées des VLANs internes sont traduites en une seule adresse publique à l'aide de PAT.

---

## Résultats

- Les VLANs ont été créés, assignés et testés avec succès.
- Le routage inter-VLAN a été testé et confirmé comme fonctionnel.
- NAT Overload (PAT) a été correctement configuré et testé pour la simulation de l'accès à Internet.
- Les ACLs ont été utilisées pour bloquer l'accès non autorisé entre certains VLANs.

--- 

## Tests & Vérifications
<img width="1918" height="1030" alt="DHCP PING" src="https://github.com/user-attachments/assets/669592c1-ec3a-4364-810c-371309b25804" />
<img width="1919" height="1030" alt="Configuration_des_VLANs" src="https://github.com/user-attachments/assets/42010ee6-a2cb-40c7-a4da-f9ab574c8d52" />

- **Binding DHCP** :
  - Vérification que les PC reçoivent les adresses IP des pools DHCP du routeur.

- **Tests de ping** :
  - Les tests de ping inter-VLAN ont été réussis.
  - Les VLANs ont été correctement segmentés et le routage entre eux a fonctionné comme prévu.

---

## Technologies utilisées

- Cisco Packet Tracer
- VLANs
- Router on a Stick
- DHCP
- NAT Overload (PAT)
- Listes de contrôle d'accès (ACL)
