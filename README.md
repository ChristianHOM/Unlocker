# Unlocker

Unlocks everything in Gd without even opening file nor downloading 
#include <Geode/Geode.hpp>
#include <Geode/modify/MenuLayer.hpp>
#include <Geode/modify/PlayLayer.hpp>

using namespace geode::prelude;

class $modify(MyMenuLayer, MenuLayer) {
    bool init() {
        if (!MenuLayer::init()) return false;
        
        // Unlock all content on game startup
        unlockAllContent();
        
        return true;
    }
    
    void unlockAllContent() {
        auto gm = GameManager::sharedState();
        
        // Unlock all player icons
        for (int i = 0; i < 200; i++) {
            gm->setPlayerIcon(i);
        }
        
        // Unlock all colors
        for (int i = 0; i < 100; i++) {
            gm->setPlayerColor(i);
        }
        
        // Unlock all ships
        for (int i = 0; i < 100; i++) {
            gm->setPlayerShip(i);
        }
        
        // Unlock all balls
        for (int i = 0; i < 100; i++) {
            gm->setPlayerBall(i);
        }
        
        // Unlock all trails
        for (int i = 0; i < 100; i++) {
            gm->setPlayerTrail(i);
        }
    }
};
