# Fejlesztési napló

## 2026. október 15. – Első tesztprojekt

Unity rendszerrel való ismerkedés.

Player Sprite(Square) létrehozása, átnevezése, Rigidbody 2D Capsule Collider 2D hozzárendelés.

Ground Sprite(Square) létrehozása és Box Collider 2D hozzárendelés

Kezdteleges PlayerMovement MonoBehaviour script létrehozás és a Playerhez rendelés

Beállításokban Edit->Project Settings->Player->Active Input Handling->Both átállítás hogy a régi és új input kezelést is fogadja.

## 2026. november 12. – Első lépések

Kezdetleges Assetek (Audio,Music,Player,Enemy,Background,Items,Tiles)

Background és Player Spirteok létrehozása azokhoz asset rendelve.

Backgroundhoz Layer orderek és size(width) módosítások, Draw Mode Tiled, Sorting layer létrehozása és background elemek hozzáadása

Playerhez Player Controller Script és Player Input 

RigidBody gravity scale és freeze rotation 

Player Input behavior invoke unity events

Player Controller Mono Sciprt 

public void OnMove(InputAction.CallbackContext context)
    {
        moveInput = context.ReadValue<Vector2>();
        IsMoving = moveInput != Vector2.zero;
    }
    
    Unity új Input Systemjével olvassa be a játékos mozgási irányát, például a WASD vagy a nyílbillentyűk segítségével.
    
    private void Awake()
    {
        rb = GetComponent<Rigidbody2D>();
    }
    
Eltárolja a Player GameObjecten található Rigidbody2D komponenst.

     private void FixedUpdate()
    {
        rb.linearVelocity = new Vector2(moveInput.x * walkSpeed,rb.linearVelocity.y);
    }
A Player vízszintes mozgását vezérli
