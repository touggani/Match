package match.informatique.cgmatane.qc.ca.match.donnee;

import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;

public class MatchDAO {

    private static MatchDAO instance = null;
    protected List<HashMap<String, String>> listeMatch;

    public static MatchDAO getInstance(){
        if(null == instance){
            instance = new MatchDAO();
        }
        return instance;
    }
    public MatchDAO() {
        this.listeMatch = new ArrayList<HashMap<String, String>>();
        preparerListeMatch();
    }

    public List<HashMap<String, String>> recupererListeMatch(){
        return listeMatch;
    }

    private void preparerListeMatch() {
        listeMatch = new ArrayList<HashMap<String, String>>();
        HashMap<String, String> match;

        match = new HashMap<String, String>();
        match.put("Equipe", "Paris Saint Germain v Liverpool");
        match.put("Date", "19 Septembre 2018");
        listeMatch.add(match);

        match = new HashMap<String, String>();
        match.put("Equipe", "Real de Madrid");
        match.put("Date", "17 Octobre 2018");
        listeMatch.add(match);

        match = new HashMap<String, String>();
        match.put("Equipe", "Bayern de Munich");
        match.put("Date", "18 Octobre 2018");
        listeMatch.add(match);
    }
}


