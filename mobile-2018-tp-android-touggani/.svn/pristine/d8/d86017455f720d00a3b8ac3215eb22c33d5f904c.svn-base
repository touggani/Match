package match.informatique.cgmatane.qc.ca.match;

import android.content.Intent;
import android.os.Bundle;
import android.support.v7.app.AppCompatActivity;
import android.util.Log;
import android.view.View;
import android.widget.AdapterView;
import android.widget.Button;
import android.widget.ListView;
import android.widget.SimpleAdapter;
import android.widget.Toast;

import java.util.HashMap;
import java.util.List;

import match.informatique.cgmatane.qc.ca.match.donnee.MatchDAO;
import match.informatique.cgmatane.qc.ca.match.vue.AjouterMatch;
import match.informatique.cgmatane.qc.ca.match.vue.ModifierMatch;

public class Match extends AppCompatActivity {

    protected ListView vueListeMatch;
    protected List<HashMap<String, String>> listeMatch;
    protected Intent intentionNaviguerAjouterMatch;
    protected MatchDAO accesseurMatch = MatchDAO.getInstance();

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.vue_match);

        Log.d("Match", "onCreate");

        vueListeMatch = (ListView)findViewById(R.id.vue_liste_match);

        listeMatch = accesseurMatch.recupererListeMatch();

        SimpleAdapter adapteur = new SimpleAdapter(this, listeMatch,
                android.R.layout.two_line_list_item,
                new String[] {"Equipe", "Date"},
                new int[] {android.R.id.text1, android.R.id.text2});

        vueListeMatch.setAdapter(adapteur);

        vueListeMatch.setOnItemClickListener(
                new AdapterView.OnItemClickListener() {
                    @Override
                    public void onItemClick(AdapterView<?> parent, View vue, int position, long id) {
                        Log.d("Match", "onItemClick");
                        ListView vueListeMatch = (ListView) vue.getParent();
                        HashMap<String, String> match = (HashMap<String, String>) vueListeMatch.getItemAtPosition((int) position);

                        //Toast message = Toast.makeText(getApplicationContext(), "Bonjour monde !", Toast.LENGTH_SHORT);
                        Toast message = Toast.makeText(getApplicationContext(), "Position : "+ position +"\nEquipe : "+ match.get("Equipe"), Toast.LENGTH_SHORT);
                        Log.d("Match", "onItemClick Position : "+position);
                        Log.d("Match", "onItemClick Equipe : "+match.get("Equipe"));

                        message.show();

                        Intent intentionNaviguerModifierMatch = new Intent(Match.this, ModifierMatch.class);

                        startActivity(intentionNaviguerModifierMatch);
                    }
                }
        );

        intentionNaviguerAjouterMatch = new Intent( this, AjouterMatch.class);

        Button actionNaviguerAjouterMatch = (Button)findViewById(R.id.action_naviguer_ajouter_match);

        actionNaviguerAjouterMatch.setOnClickListener(
                new View.OnClickListener(){
                    public void onClick(View arg0){
                        startActivity(intentionNaviguerAjouterMatch);
                    }
                }
        );
    }

    /*
    private List<HashMap<String, String>> preparerListeMatch() {
        List<HashMap<String, String>> listeMatch = new ArrayList<HashMap<String, String>>();
        HashMap<String, String> match;

        match = new HashMap<String, String>();
        match.put("Titre", "Glacé");
        match.put("Auteur", "Bernard Minier");
        listeMatch.add(match);

        match = new HashMap<String, String>();
        match.put("Titre", "Les fourmis");
        match.put("Auteur", "Bernard Werber");
        listeMatch.add(match);

        match = new HashMap<String, String>();
        match.put("Titre", "M. Mercedes");
        match.put("Auteur", "Stephen King");
        listeMatch.add(match);

        return listeMatch;
    }
    */
}