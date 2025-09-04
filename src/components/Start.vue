<script setup lang="ts">
import { useStore } from '../store';

const store = useStore();
const onClick = () => store.count++;
</script>

<template>
    <div class="ct-container ct-p-4">
        <div class="ct-card">
            <div class="ct-card-header">
                <h2 class="ct-h2 ct-mb-0 ct-text-center">Churchtools Dashboard</h2>
            </div>
            <div class="ct-card-body ct-text-center">
                <p class="ct-mb-3">Dieses Modul hilft, das ChurchTools System zu überwachen</p>
                
                <div class="ct-mb-4">
                    <h5 class="ct-h5 ct-mb-2">System-Überwachung</h5>
                    <p>Behalten Sie den Überblick über wichtige Kennzahlen und Aktivitäten in Ihrem ChurchTools System.</p>
                </div>
                
                <div class="ct-d-flex ct-justify-content-center ct-mb-3" style="gap: 0.5rem;">
                    <button class="ct-btn ct-btn-primary" @click="onClick">
                        Dashboard testen
                    </button>
                    <router-link to="/ui" class="ct-btn ct-btn-secondary">
                        UI-Komponenten
                    </router-link>
                </div>
                
                <div v-if="store.count > 0" class="ct-card">
                    <div class="ct-card-body">
                        <small>Dashboard-Interaktionen: {{ store.count }}</small>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Dashboard Features -->
        <div class="ct-card ct-mb-4" style="margin-top: 2rem;">
            <div class="ct-card-header">
                <h4 class="ct-h4 ct-mb-0">Dashboard Features</h4>
            </div>
            <div class="ct-card-body">
                <div class="feature-grid">
                    <div class="feature-item">
                        <h6 class="ct-h6">👥 Anzahl User</h6>
                        <p>Überwachung der aktiven Benutzer und Registrierungen im System</p>
                    </div>
                    <div class="feature-item">
                        <h6 class="ct-h6">📊 Hauptaktivitäten</h6>
                        <p>Monitoring der wichtigsten Systemaktivitäten und Nutzungsstatistiken</p>
                    </div>
                    <div class="feature-item">
                        <h6 class="ct-h6">⚠️ Fehler</h6>
                        <p>Erkennung und Anzeige von Systemfehlern und kritischen Ereignissen</p>
                    </div>
                    <div class="feature-item">
                        <h6 class="ct-h6">📈 Echtzeit-Monitoring</h6>
                        <p>Live-Überwachung aller wichtigen Systemmetriken und Performance-Indikatoren</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.feature-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: var(--ct-spacing-md);
    margin-top: var(--ct-spacing-md);
}

/* Responsive grid: mobile 1 column, desktop 2x2 */
@media (min-width: 768px) {
    .feature-grid {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 767px) {
    .feature-grid {
        grid-template-columns: 1fr;
    }
}

.feature-item {
    padding: var(--ct-spacing-md);
    border: 1px solid var(--ct-border-light);
    border-radius: 0.25rem;
    background-color: var(--ct-bg-secondary);
}

.feature-item h6 {
    color: var(--ct-primary);
    margin-bottom: var(--ct-spacing-sm);
}

.feature-item p {
    color: var(--ct-text-secondary);
    font-size: 0.875rem;
    margin-bottom: 0;
}
</style>
