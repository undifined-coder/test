# test

class Players{

    constructor(health,strength,attack)
    {
        this.health=health;
        this.strength=strength;
        this.attack=attack;
    }


}

function roll()
{
    return Math.floor(Math.random() * 6) + 1;
}


function battledamage(attacker,defender)
{
    const attacker_roll=roll();
    const defender_roll=roll();

    const attacker_power=attacker_roll*attacker.attack;
    const defender_power=defender_roll*defender.strength;


    if(attacker_power>defender_power)
    {
        return attacker_power-defender_power;
    }

    else
    return 0;


}

function arena(player_one,player_two )
    {   const attacking_player=0;
        const defending_player=0;
        const level=1;

        while(player_one.health!=0 && player_two.health!=0)
        {
        if(level==1)
        {
            if(player_one.health>player_two.health)
        {
            attacking_player=player_one;
            defending_player=player_two;

        }

        else
        {
            attacking_player=player_two;
            defending_player=player_one;    
        }
    }
        
        else
        {
            [attacking_player,defending_player]=[player_two,player_one];

        }
        const damage=battledamage(attacking_player,defending_player);

         defending_player.health=defending_player.health-damage;

         level++;

        }

        if(player_two.health==0)
        {
            console.log("Player One is Winner");
        }

        else
        {
            console.log("Player two Is Winner")
        }
    
    }


    const player_one = new Players(50, 5, 10);
    const player_two = new Players(100, 10, 5)


    arena(player_one,player_two);

